---
layout: page
permalink: /my_resume/
---
<style>
	html,
	body,
	div,
	p {
		margin: 0;
		padding: 0
	}

	body {
		font-size: 14px;
		font-family: "microsoft yahei";
		background-color: #ffffff
	}

	table {
		border-collapse: collapse;
		border-spacing: 0;
		table-layout: fixed;
		margin-bottom: 0px;
		border-color: rgba(255,255,255,0);
	}
	
	table th {
		padding: 0px;
	}
	
	table td {
		padding: 0px;
	}
	
	table td {
		border-width: 0px;
	}

	th,
	td {
		font-size: 14px;
		padding: 0
	}
	
	table tr:nth-child(even) {
		background-color: rgba(255,255,255,0);
	}

	a {
		text-decoration: none
	}

	img {
		border: 0 none
	}

	.blue {
		text-decoration: none;
		color: #3c3d5d
	}

	.chead {
		width: 1002px
	}

	.chead .logo {
		width: 698px;
		height: 90px
	}

	.chead .txt {
		width: 152px;
		height: 90px
	}

	.column {
		width: 1002px;
		line-height: 28px;
		border: 1px solid #dedede
	}

	.column .hbox {
		width: 185px;
		height: 154px
	}

	.column .head {
		display: block;
		background-color: #fafafa
	}

	.column .box {
		width: 100%;
		background-color: #ffffff;
		border-top: 2px solid #f2f3f5
	}

	.column .box1 {
		width: 100%;
		word-wrap: break-word;
		color: #ffffff;
		background-color: #3f4160
	}

	.column .box2 {
		width: 100%;
		background-color: #f8f9fa
	}

	.column .tba {
		width: 940px;
		padding: 0 30px 15px
	}

	.column .tbb {
		width: 940px;
		padding: 0 30px
	}

	.column .tb1 {
		width: 900px;
		line-height: 28px;
		color: #333333;
		word-break: break-all;
		padding: 0 20px
	}

	.column .tb2 {
		width: 430px;
		padding: 0 20px
	}

	.column .tb3 {
		width: 900px;
		padding: 15px 20px 15px 0
	}

	.column .gray,
	.column .gray2 {
		color: #999999;
		word-break: break-all
	}

	.column .gray2 {
		color: #666666
	}

	.column .plate1,
	.column .plate2 {
		width: 430px;
		height: 54px;
		font-size: 16px;
		font-weight: bold;
		color: #818ba3
	}

	.column .plate1 {
		width: 900px;
		padding: 0 50px
	}

	.column .plate1 .f16 {
		font-size: 14px;
		font-weight: normal;
		color: #333333
	}

	.column .plate1 .f12 {
		font-size: 12px;
		font-weight: normal;
		color: #999999
	}

	.column .keys,
	.column .keys2 {
		width: 85px;
		line-height: 28px;
		color: #666666
	}

	.column .keys2 {
		width: 110px
	}

	.column .txt1,
	.column .txt2,
	.column .txt3 {
		width: 815px;
		line-height: 28px;
		color: #333333;
		word-break: break-all
	}

	.column .txt2 {
		width: 345px
	}

	.column .txt3 {
		width: auto;
		max-width: 815px;
		font-size: 14px;
		font-weight: bold
	}

	.column .txt4 {
		width: 305px;
		color: #ffffff;
		word-break: break-all
	}

	.column .infr {
		width: 767px;
		color: #ffffff;
		table-layout: auto
	}

	.column .vam,
	.column .grcha {
		vertical-align: middle;
		margin-left: 5px
	}

	.column .box1 .vam {
		margin-right: 5px;
		margin-left: 0
	}

	.column .name {
		font-size: 24px;
		padding-bottom: 18px
	}

	.column .icard {
		color: #a1a3ae;
		padding-bottom: 18px
	}

	.column .con {
		border-top: 1px dotted #ddd
	}

	.column .pr20 {
		width: 225px;
		padding-right: 20px
	}

	.column .time {
		width: 120px;
		line-height: 28px;
		color: #666666;
		padding-left: 20px
	}

	.column .rtbox {
		width: 765px;
		line-height: 28px;
		color: #333333;
		padding: 0 20px 0 15px;
		word-break: break-all
	}

	.column .hai,
	.column .guan {
		line-height: 18px;
		font-size: 12px;
		color: #ffffff;
		vertical-align: text-top;
		margin-left: 5px;
		padding: 1px 3px;
		background-color: #3cbe7f;
		border-radius: 2px
	}

	.column .guan {
		background-color: #ff9f20
	}

	.column .tag {
		display: inline-block;
		word-break: break-all;
		#display: inline;
		#zoom: 1
	}

	.column .all {
		color: #666;
		padding: 10px 20px;
		background-color: #fafafa
	}

	.column .tit {
		width: 900px;
		height: 40px;
		color: #666666;
		padding: 0 20px;
		background-color: #f5f5f5
	}

	.column .p15 {
		padding: 15px 0
	}

	.column .p5 {
		display: inline-block;
		color: #666666;
		padding: 0 5px;
		#display: inline;
		#zoom: 1
	}

	.column .cell .skill {
		width: 165px;
		text-align: right;
		padding-right: 15px
	}

	.column .cell .skbg,
	.column .cell .skco {
		display: inline-block;
		width: 245px;
		height: 18px;
		line-height: 18px;
		font-size: 12px;
		color: #ffffff;
		vertical-align: top;
		margin-top: 6px;
		background-color: #dddddd;
		border-radius: 20px;
		#display: inline;
		#zoom: 1
	}

	.column .cell .skco {
		width: 235px;
		font-style: normal;
		margin-top: 0;
		padding-left: 10px;
		background-color: #ff9f20;
		z-index: 3
	}

	.column .sl .skco {
		width: 173px
	}

	.column .lh .skco {
		width: 112px
	}

	.column .yb .skco {
		width: 51px
	}

	.column .fbox strong {
		font-size: 14px;
		font-weight: bold
	}

	.column .cha {
		font-size: 12px;
		font-weight: normal;
		color: #00457d;
		margin-left: 5px
	}

	.column .cha:hover {
		color: #ff6000
	}

	.column .email {
		width: 330px
	}

	.eng td,
	.eng .txt3,
	.eng .fbox strong {
		font-size: 13px;
		font-family: 'Arial'
	}

	.eng .txt1,
	.eng .rtbox,
	.eng .phd {
		width: 775px;
		font-size: 13px;
		font-family: 'Arial';
		line-height: 28px
	}

	.eng .txt2 {
		width: 305px
	}

	.eng .txt4 {
		width: 245px
	}

	.eng .cell .txt3 {
		width: 120px
	}

	.eng .time,
	.eng .keys {
		width: 110px;
		font-size: 13px;
		text-align: right
	}

	.eng .cell .skill {
		width: 130px
	}

	.eng .phd {
		padding-left: 145px
	}

	.eng .keys {
		padding-right: 15px
	}

	.eng .pr20 {
		width: 205px
	}

	.eng .pr20 .keys {
		width: 100px
	}

	.eng .email {
		width: 270px
	}
</style>
<table cellpadding="0" cellspacing="0" align="center" bgcolor="#fff" class="column">
	<tbody>
		<tr>
			<td valign="top">
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box1">
					<tbody>
						<tr>
							<td class="hbox" align="middle"><img src="http://i.51job.com/resume/ajax/image.php?type=avatar&amp;userid=84217310&amp;key=266176664df7251286fd2c40069de31d"
								 width="85" height="104" class="head" alt="头像"></td>
							<td>
								<table cellspacing="0" cellpadding="0" border="0" class="infr">
									<tbody>
										<tr>
											<td colspan="2" class="name">朱益锋</td>
											<td align="right" class="icard">
												ID:84217310</td>
										</tr>
										<tr>
											<td valign="top">
												<img class="vam" src="http://img01.51jobcdn.com/im/2016/resume/y1.png" width="20" height="20">观望有好机会会考虑</td>
											<td valign="top">
												<img class="vam" src="http://img01.51jobcdn.com/im/2016/resume/y2.png" width="20" height="20">15356032778</td>
											<td valign="top">
												<table cellspacing="0" cellpadding="0" border="0" class="email">
													<tbody>
														<tr>
															<td valign="top" width="25"><img class="vam" src="http://img01.51jobcdn.com/im/2016/resume/y3.png" width="20"
																 height="20"></td>
															<td valign="top" class="txt4">994613212@qq.com</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td valign="top" colspan="3">
												<p><img class="vam" src="http://img01.51jobcdn.com/im/2016/resume/y4.png" width="20" height="20">男<span
													 class="p5">|</span>31 岁 (1988/02/21)<span class="p5">|</span>现居住宁波<span class="p5">|</span>7年工作经验
												</p>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box2">
					<tbody>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td valign="top" class="tb2">
												<table cellspacing="0" cellpadding="0" border="0">
													<thead style="height:0">
														<tr>
															<td valign="top" class="keys"></td>
															<td valign="top" class="txt2"></td>
														</tr>
													</thead>
													<tbody>
														<tr>
															<td colspan="2" class="plate2">最近工作</td>
														</tr>
														<tr>
															<td valign="top" class="keys">职位：</td>
															<td valign="top" class="txt2">手机软件开发工程师</td>
														</tr>
														<tr>
															<td valign="top" class="keys">公司：</td>
															<td valign="top" class="txt2">宁波希韵信息科技有限公司</td>
														</tr>
														<tr>
															<td valign="top" class="keys">行业：</td>
															<td valign="top" class="txt2">计算机软件</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td valign="top" class="tb2">
												<table cellspacing="0" cellpadding="0" border="0">
													<thead style="height:0">
														<tr>
															<td valign="top" class="keys"></td>
															<td valign="top" class="txt2"></td>
														</tr>
													</thead>
													<tbody>
														<tr>
															<td colspan="2" class="plate2">最高学历/学位</td>
														</tr>
														<tr>
															<td valign="top" class="keys">专业：</td>
															<td valign="top" class="txt2">经济管理</td>
														</tr>
														<tr>
															<td valign="top" class="keys">学校：</td>
															<td valign="top" class="txt2">齐鲁工业大学</td>
														</tr>
														<tr>
															<td valign="top" class="keys">学历/学位：</td>
															<td valign="top" class="txt2">本科</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">个人信息</td>
						</tr>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">微信号：
															</td>
															<td valign="top" class="txt2">zhuyifeng570</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">户口/国籍：</td>
															<td valign="top" class="txt2">宁波</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">身高：</td>
															<td valign="top" class="txt2">175cm</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">婚姻状况：</td>
															<td valign="top" class="txt2">已婚</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">家庭地址：</td>
															<td valign="top" class="txt2">宁波
																(邮编：315141)
															</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">政治面貌：</td>
															<td valign="top" class="txt2">共青团员</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">
								目前年收入
								<span>&nbsp;18.2万元</span><span class="f12">（包含基本工资、补贴、奖金、股权收益等）</span>
							</td>
						</tr>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td class="tb1">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td class="pr20">
																<table cellspacing="0" cellpadding="0" border="0">
																	<tbody>
																		<tr>
																			<td class="keys2">基本工资：</td>
																			<td valign="middle" class="txt">1.4万元
																			</td>
																		</tr>
																	</tbody>
																</table>
															</td>
															<td class="pr20">
																<table cellspacing="0" cellpadding="0" border="0">
																	<tbody>
																		<tr>
																			<td class="keys">补贴/津贴：</td>
																			<td valign="middle" class="txt">0万元
																			</td>
																		</tr>
																	</tbody>
																</table>
															</td>
															<td class="pr20">
																<table cellspacing="0" cellpadding="0" border="0">
																	<tbody>
																		<tr>
																			<td class="keys">奖金/佣金：</td>
																			<td valign="middle" class="txt">1.4万元
																			</td>
																		</tr>
																	</tbody>
																</table>
															</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">求职意向</td>
						</tr>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td class="tb1" colspan="2">
												<table cellspacing="0" cellpadding="0" border="0">
													<thead style="height:0">
														<tr>
															<td valign="top" class="keys"></td>
															<td valign="top" class="txt1"></td>
														</tr>
													</thead>
													<tbody>
														<tr>
															<td valign="top" class="keys">个人标签：</td>
															<td valign="top" class="txt1">
																<span class="tag">iOS开发工程师&nbsp;&nbsp;</span><span class="tag">iOS高级开发工程师</span>
															</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">期望薪资：</td>
															<td valign="top" class="txt2">15000
																元/月
															</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">地点：</td>
															<td valign="top" class="txt2"><span class="tag">宁波</span></td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">职能/职位：</td>
															<td valign="top" class="txt2">
																<span class="tag">手机软件开发工程师
																</span><span class="tag">&nbsp;&nbsp;iOS开发工程师</span>
															</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">行业：</td>
															<td valign="top" class="txt2"><span class="tag">计算机软件</span></td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">到岗时间：</td>
															<td valign="top" class="txt2">1个月内</td>
														</tr>
													</tbody>
												</table>
											</td>
											<td class="tb2" valign="top">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="keys">工作类型：</td>
															<td valign="top" class="txt2">全职</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
										<tr>
											<td class="tb1" colspan="2">
												<table cellspacing="0" cellpadding="0" border="0">
													<thead style="height:0">
														<tr>
															<td valign="top" class="keys"></td>
															<td valign="top" class="txt1"></td>
														</tr>
													</thead>
													<tbody>
														<tr>
															<td valign="top" class="keys">自我评价：</td>
															<td valign="top" class="txt1">1、熟悉OC，熟悉Swift，了解Java&#x20;se<br>2、遵循iOS设计规范，提供后台接口设计方案，坚持最佳实践<br>3、2017年公司优秀员工<br>4、Github:&#x20;https://github.com/zyfilife<br>5、个人博客：https://zyfilife.github.io<br>6、简书:&#x20;https://www.jianshu.com/u/37e93d07afb1<br>7、熟悉各类业务代码、目前主要工作是项目核心技术研发<br>8、考虑如何从市场角度、用户角度去实现相关功能、业务逻辑<br>9、公司在镇海、家住鄞州区下应街道。目前想换一家离家近的公司</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">工作经验</td>
						</tr>
						<tr>
							<td class="tbb">
								<table cellspacing="0" cellpadding="0" border="0">
									<tr>
										<td class="p15">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2017/9-至今</td>
														<td valign="top" class="rtbox">
															<strong class="txt3">手机软件开发工程师</strong><span class="p5">|</span><span>研发部</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1" colspan="2">
															<span>宁波希韵信息科技有限公司</span><span class="gray">&nbsp;[1年6个月]
															</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1 gray2" colspan="2">计算机软件<span class="p5">|</span>少于50人<span class="p5">|</span>民营公司</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">工作描述：</td>
																		<td valign="top" class="txt1">负责《海伦智能陪练》iPad端和iPhone端开发<br>负责开源c++项目二次研发<br>《海伦智能陪练》项目负责人</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
									<tr>
										<td class="p15 con">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2016/5-2017/7</td>
														<td valign="top" class="rtbox">
															<strong class="txt3">iOS开发工程师</strong><span class="p5">|</span><span>研发部</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1" colspan="2">
															<span>浙江正道远网络科技有限公司</span><span class="gray">&nbsp;[1年2个月]
															</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1 gray2" colspan="2">计算机软件<span class="p5">|</span>50-150人<span class="p5">|</span>民营公司</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">工作描述：</td>
																		<td valign="top" class="txt1">单独负责《学之路》iOS端开发</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
									<tr>
										<td class="p15 con">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2015/3-2016/5</td>
														<td valign="top" class="rtbox">
															<strong class="txt3">iOS软件开发工程师</strong><span class="p5">|</span><span>技术研发部</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1" colspan="2">
															<span>宁波市骏远信息技术服务有限公司</span><span class="gray">&nbsp;[1年2个月]
															</span>
														</td>
													</tr>
													<tr>
														<td class="phd tb1 gray2" colspan="2">计算机软件<span class="p5">|</span>少于50人<span class="p5">|</span>民营公司</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">工作描述：</td>
																		<td valign="top" class="txt1">《骏远镖局货主版》《骏远镖局司机版》《沁园网点》iOS端开发</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">项目经验</td>
						</tr>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tr>
										<td class="p15">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2017/9-至今</td>
														<td valign="top" class="rtbox"><strong>海伦智能陪练</strong></td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">所属公司：</td>
																		<td valign="top" class="txt1">宁波希韵信息科技有限公司</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">项目描述：</td>
																		<td valign="top" class="txt1">项目简介：钢琴教育类App，在App上展示钢琴曲谱，提供多种弹奏模式，通过蓝牙或者USB连接智能钢琴，实时收集用户弹奏数据，最后将弹奏数据分析总结后呈现给用户，帮助用户提高钢琴弹奏水平<br>开发语言：OC、Swift</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">责任描述：</td>
																		<td valign="top" class="txt1">负责iPad端和iPhone端开发<br>MIDI框架应用<br>曲谱弹奏算法开发和优化<br>蓝牙、USB数据通信功能开发<br>打谱软件C++开源项目二次开发</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
									<tr>
										<td class="p15 con">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2016/5-2017/7</td>
														<td valign="top" class="rtbox"><strong>学之路</strong></td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">所属公司：</td>
																		<td valign="top" class="txt1">浙江正道远网络科技有限公司</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">项目描述：</td>
																		<td valign="top" class="txt1">教育管理+家校互联<br>项目语言：Swift<br>模块介绍：教师端-校信、办公应用、作业、个人中心、班级圈、个人网盘；学生端-校信、作业、学习、个人中心、班级圈。<br>框架介绍：MVC模式，独立网络请求处理层，组件化设计。<br>应用技能：推送，即时通讯，支付，分享，地图，视频录制、播放，语音录制、播放，打印，富文本，核心动画，本地缓存等等。</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">责任描述：</td>
																		<td valign="top" class="txt1">单人负责iOS手机端开发。</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
									<tr>
										<td class="p15 con">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2015/9-2016/5</td>
														<td valign="top" class="rtbox"><strong>《骏远镖局货主版》《骏远镖局司机版》</strong></td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">所属公司：</td>
																		<td valign="top" class="txt1">宁波市骏远信息技术服务有限公司</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">项目描述：</td>
																		<td valign="top" class="txt1">物流服务平台APP,货主发布货源信息，快速寻找优质货车司机资源，全程监控运输流程。司机快速寻找高价货源，方便快速地达成订单并完成运输流程。</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">责任描述：</td>
																		<td valign="top" class="txt1">iOS版开发</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
									<tr>
										<td class="p15 con">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2015/4-2015/7</td>
														<td valign="top" class="rtbox"><strong>沁园网点</strong></td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">项目描述：</td>
																		<td valign="top" class="txt1">网点管理类App</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">责任描述：</td>
																		<td valign="top" class="txt1">iOS版开发</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" class="box">
					<tbody>
						<tr>
							<td class="plate1">教育经历</td>
						</tr>
						<tr>
							<td class="tba">
								<table cellspacing="0" cellpadding="0" border="0">
									<tr>
										<td class="p15">
											<table cellspacing="0" cellpadding="0" border="0">
												<tbody>
													<tr>
														<td valign="top" class="time">2008/9-2012/7</td>
														<td valign="top" class="rtbox"><strong>齐鲁工业大学</strong></td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">本科<span class="p5">|</span>经济管理</td>
													</tr>
													<tr>
														<td class="tb1" colspan="2">
															<table cellspacing="0" cellpadding="0" border="0">
																<tbody>
																	<tr>
																		<td valign="top" class="keys">专业描述：</td>
																		<td valign="top" class="txt1">管理学、微观经济学、宏观经济学、管理信息系统、统计学、会计学、财务管理、市场营销、经济法、消费者行为学、国际市场营销、市场调查等课程</td>
																	</tr>
																</tbody>
															</table>
														</td>
													</tr>
												</tbody>
											</table>
										</td>
									</tr>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
				<table xmlns="" cellspacing="0" cellpadding="0" border="0" class="box">
					<tbody>
						<tr>
							<td class="plate1">
								技能特长
								<span class="f12">（包括IT技能、语言能力、证书、成绩、培训经历）</span>
							</td>
						</tr>
						<tr>
							<td class="tbb">
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td class="tit">技能/语言</td>
										</tr>
										<tr>
											<td class="p15">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td class="tb2 cell lh" valign="top">
																<table cellspacing="0" cellpadding="0" border="0">
																	<tbody>
																		<tr>
																			<td class="skill"><strong class="txt3">英语</strong></td>
																			<td valign="top"><span class="skbg"><span class="skco">良好</span></span></td>
																		</tr>
																	</tbody>
																</table>
															</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
								<table cellspacing="0" cellpadding="0" border="0">
									<tbody>
										<tr>
											<td class="tit">证书</td>
										</tr>
										<tr>
											<td class="tb3">
												<table cellspacing="0" cellpadding="0" border="0">
													<tbody>
														<tr>
															<td valign="top" class="time">2013/4</td>
															<td valign="top" class="rtbox">
																<strong class="txt3">大学英语四级</strong><span>
																	（517）
																</span>
															</td>
														</tr>
													</tbody>
												</table>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
	</tbody>
</table>
