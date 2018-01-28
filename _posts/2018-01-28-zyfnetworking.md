---
title: "ZYFNetworking"
date: 2018-01-28 14:20:35
editor: 朱益锋
---

> 简介：基于AFNetworking封装的轻量级网络请求框架

### 数据请求

```
-(void)                  get:(NSString *)urlString
              withParameters:(id)parameters
             timeoutInterval:(NSTimeInterval)timeoutInterval
                showDebugLog:(BOOL)showDebugLog
 responseObjectCachedHandler:(ZYFNCacheHandler) responseObjectCachedHandler
           completionHandler:(ZYFNCompletionHandler)completionHandler
{
    if (responseObjectCachedHandler) {
        id responseObjectCached = [_cacheManger responseObjectForUrlString:urlString
                                                                parameters:parameters];
        responseObjectCachedHandler(responseObjectCached);
    }
    NSDictionary *params = [NSDictionary dictionaryWithDictionary:parameters];
    self.http_manager.requestSerializer.timeoutInterval = timeoutInterval;
    [self.http_manager GET:urlString
                   parameters:params
                     progress:nil
                      success:^(NSURLSessionDataTask * _Nonnull task, id  _Nullable responseObject) {
                          if (showDebugLog) {
                              [self debugLogWithMethod:@"GET" urlString:urlString parameters:parameters responseObject:responseObject error:nil];
                          }
                          if (responseObjectCachedHandler) {
                              [_cacheManger cacheWithResponseObject:responseObject urlString:urlString parameters:parameters completedHandler:nil];
                          }
                          completionHandler(task, responseObject, nil);
                      }
                      failure:^(NSURLSessionDataTask * _Nullable task, NSError * _Nonnull error) {
                          if (showDebugLog) {
                              [self debugLogWithMethod:@"GET" urlString:urlString parameters:parameters responseObject:nil error:error];
                          }
                          completionHandler(task, nil, error);
                      }];
}
```

### 错误处理

```
- (BOOL)hasErrorAndCalledBack:(id)responseObject
                        error:(NSError *)error
               failureHandler:(ZYFNFailureHandler)failureHandler
{
    if (error != nil) {
        if (failureHandler) {
            failureHandler(error);
        }
        return true;
    }else {
        if (responseObject == nil) {
            failureHandler([self getEmptyError]);
            return true;
        }
        if ([responseObject isKindOfClass:[NSDictionary class]]) {
            NSError *customError = [self getCustomErrorWithDictionary:responseObject];
            if (customError != nil) {
                if (customError.code == code_tokenInValid) {
                    [NSNotificationCenter.defaultCenter postNotificationName:kNotificationTokenInvalid object:nil];
                }
                if (failureHandler) {
                    failureHandler(customError);
                }
                return true;
            }else {
                return false;
            }
        }else {
            if (failureHandler) {
                failureHandler([self getPrasingError]);
            }
            return true;
        }
    }
}

-(NSError *)getCustomErrorWithDictionary:(NSDictionary *)dictionary
{
    id code = [dictionary objectForKey:key_error];
    NSString *message = [dictionary objectForKey:key_message];
    if (code == nil || [code isKindOfClass:[NSNull class]] || message == nil) {
        return nil;
    }
    
    NSInteger statusCode;
    if ([code isKindOfClass:[NSString class]] || [code isKindOfClass:[NSNumber class]] ) {
        statusCode = [code integerValue];
    }else {
        statusCode = (NSInteger) code;
    }
    
    if (statusCode != code_success) {
        
        NSDictionary *errorUserInfo = @{NSLocalizedDescriptionKey: message};
        NSError *error = [[NSError alloc] initWithDomain:kDomain code:statusCode userInfo:errorUserInfo];
        NSLog(@"WebServers Error: %@ ErrorCode: %ld", message, (long)statusCode);
        
        return error;
    }
    
    return nil;
}

- (NSError *)getEmptyError
{
    NSDictionary *errorUserInfo = @{NSLocalizedDescriptionKey: @"数据为空"};
    NSError *error = [[NSError alloc] initWithDomain:kDomain code:-99001 userInfo:errorUserInfo];
    NSLog(@"JSONPrasing Error: %@ ErrorCode: %d", @"数据为空", -99001);
    return error;
}

- (NSError *)getPrasingError
{
    NSDictionary *errorUserInfo = @{NSLocalizedDescriptionKey: @"数据解析失败,请检查数据类型是否正确"};
    NSError *error = [[NSError alloc] initWithDomain:kDomain code:-99002 userInfo:errorUserInfo];
    NSLog(@"JSONPrasing Error: %@ ErrorCode: %d", @"数据解析失败,请检查数据类型是否正确", -99002);
    return error;
}
```

### 数据解析

```


- (NSDictionary *)getDictionaryOrCallbackWithError:(NSString *)key
                                    responseObject:(id)responseObject
                                             error:(NSError *)error
                                    failureHandler:(ZYFNFailureHandler)failureHandler
{
    id value = [self getValueOrCallbackWithError:key
                                  responseObject:responseObject
                                           error:error
                                  failureHandler:failureHandler];
    if (!value) {
        return nil;
    }else {
        if ([value isKindOfClass:[NSDictionary class]]) {
            return value;
        }else {
            failureHandler([self getPrasingError]);
        }
    }
    return nil;
}

-(NSArray *)getArrayOrCallbackWithError:(NSString *)key
                         responseObject:(id)responseObject
                                  error:(NSError *)error
                         failureHandler:(ZYFNFailureHandler)failureHandler
{
    id value = [self getValueOrCallbackWithError:key
                                  responseObject:responseObject
                                           error:error
                                  failureHandler:failureHandler];
    if (!value) {
        return nil;
    }else {
        if ([value isKindOfClass:[NSArray class]]) {
            return value;
        }else {
            failureHandler([self getPrasingError]);
        }
    }
    return nil;
}

-(id)getValueOrCallbackWithError:(NSString *)key
                  responseObject:(id)responseObject
                           error:(NSError *)error
                  failureHandler:(ZYFNFailureHandler)failureHandler
{
    if (![self hasErrorAndCalledBack:responseObject
                               error:error
                      failureHandler:failureHandler]) {
        if (key == nil) {
            return responseObject;
        }else {
            if ([responseObject isKindOfClass:[NSDictionary class]]) {
                id value = [(NSDictionary *)responseObject objectForKey:key];
                return value;
            }
        }
    }
    return nil;
}
```
