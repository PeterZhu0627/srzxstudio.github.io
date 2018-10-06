
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<title>世界时钟-为您提供世界各地现在时间和日期-时间地图网</title>
<meta name="keywords" content="世界时钟,现在时间,日期,时间地图"/>
<meta name="description" content="时间地图网（www.24timemap.com）为您提供全球各地现在时间几点几分几秒，以及它们的时区时间、日期，准确的世界时钟，在这里了解世界！"/>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="mobile-agent" content="format=[wml|xhtml|html5]; url=http://m.24timemap.com/"/>
<meta name="baidu_union_verify" content="b66f43225108b8008fc203260ee01ed8">
<link rel="stylesheet" type="text/css" href="/static/css/global.css"/>
<link rel="stylesheet" type="text/css" href="/static/css/time.css"/>
<link rel="stylesheet" type="text/css" href="/static/css/map.css"/>
<script type="text/javascript" src="/static/js/style.js"></script>
<script type="text/javascript" src="/static/js/asia_shijian.js"></script>
<script type="text/javascript" src="/static/js/boxCont.js"></script>
<script type="text/javascript" src="/static/js/qian.js"></script>
<script type="text/javascript" src="/static/js/uaredirect.js"></script>
<script type="text/javascript">var url=window.location.href;var uu=url.replace("www", "m");uaredirect(uu);</script>
<SCRIPT LANGUAGE="JavaScript">
var timerID; var past_time=0;
function tzone(ts) { this.ct = new Date(0); this.ts = ts; }
function UpdateClocks() {past_time++;
var ct = new Array(new tzone(1538826356),new tzone(1538779556),new tzone(1538833556),new tzone(1538801156),new tzone(1538829956),new tzone(1538826356),new tzone(1538797556)) ;
    var dt = new Date() ;
    var startDST = new Date(dt.getFullYear(), 3, 1) ;
    while (startDST.getDay() != 0) startDST.setDate(startDST.getDate() + 1) ;
    var endDST = new Date(dt.getFullYear(), 9, 31) ;
    while (endDST.getDay() != 0) endDST.setDate(endDST.getDate() - 1) ;
    var ds_active ;
    if (startDST < dt && dt < endDST) ds_active = 1; else ds_active = 0;
    var printstr = "";
    gmdt = new Date();
    for (n=0 ; n<ct.length ; n++) {
        ct[n].ct = new Date((ct[n].ts+past_time) * 1000) ;
    }
document.getElementById('Clockk0').innerHTML = ClockString(ct[0].ct);
document.getElementById('Clockk1').innerHTML = ClockString(ct[1].ct);
document.getElementById('Clockk2').innerHTML = ClockString(ct[2].ct);
document.getElementById('Clockk3').innerHTML = ClockString(ct[3].ct);
document.getElementById('Clockk4').innerHTML = ClockString(ct[4].ct);
document.getElementById('Clockk5').innerHTML = ClockString(ct[5].ct);
document.getElementById('Clockk6').innerHTML = ClockString(ct[6].ct);
timerID = window.setTimeout("UpdateClocks()", 1001);}
function ClockString(dt) {
	var stemp ;
	var dt_year = dt.getUTCFullYear();
	var dt_month = dt.getMonth() + 1;
	var dt_day = dt.getDate();
	var dt_hour = dt.getHours();
	var dt_minute = dt.getMinutes();
	var dt_second = dt.getSeconds();
	dt_year = dt_year.toString();
	if (dt_hour < 10) dt_hour = '0' + dt_hour ;
	if (dt_minute < 10) dt_minute = '0' + dt_minute ;
	if (dt_second < 10) dt_second = '0' + dt_second ;
	//stemp = dt_month + '月' + dt_day + '日';
	stemp = ' <span>' + dt_hour + "</span>:<span>" + dt_minute + "</span>:<span>" + dt_second + "</span>";
	return stemp ;
}
</script>
</head>
<body onload="UpdateClocks();">
<div class="header">
<div class="logo"><a href="http://www.24timemap.com/"><img src="/static/img/time_logo.gif" title="时间地图网"></a></div>
<div class="head_r"><script>global_tb();</script></div>
</div>
<div class="big_gsearch">
<span class="src_btn">查找</span>
<form action="/search" method="post">
<input id="serch_text" class="search_area" type="text" value="输入城市" onfocus="this.value='';" onblur="if(this.value==''){this.value='输入城市';}" name="city">
<input class="search_btn" type="submit" value="">
</form>
</div>
<div class="menu">
<ul>
<li class="current"><a href="/" title=""><span>首页</span></a></li>
<li><a href="/world" title=""><span>世界时间</span></a></li>
<li><a href="/usa" title=""><span>美国时间</span></a></li>
<li><a href="http://www.24timemap.com/uk" title=""><span>英国时间</span></a></li>
<li><a href="/canada" title=""><span>加拿大时间</span></a></li>
<li><a href="/world/europe" title=""><span>欧洲时间</span></a></li>
<li><a href="/sun" title=""><span>日出日落</span></a></li>
<li><a href="/moon" title=""><span>月出月落</span></a></li>
<li><a href="/distance" title=""><span>距离计算器</span></a></li>
<li><a href="/difference" title=""><span>时差计算器</span></a></li>
</ul>
</div>
<div class="block10"></div>
<div class="c1000">
<div class="info"><p>现在几点了？时间地图网拥有世界上最全的城市时间信息，我们致力于提供全球每一个城市的当前标准现在时间以及时差，并且包括夏令时、日出日落、月出月落等信息！可通过我们进行时间校准，我们是您出差、旅游的好帮手！</p><h1>世界时间地图</h1></div>
<div class="block10"></div>
<div class="mapbig" style="width:1000px;position:relative;">
<div class="imgmap" style="position:relative"><img src="/static/img/world_clock_map.jpg" width="1000" height="512" id="main_map"/>
</div>
</div>
<div class="block10"></div>
<div class="ss_city">
<span class="txt">搜索城市</span>
<form action="/search" method="post">
<input class="ss_txt" type="text" value="输入城市" onfocus="this.value='';" onblur="if(this.value==''){this.value='输入城市';}" name="city">
<input class="ss_btn" value="查询" type="submit">
</form>
</div>
<div class="block15"></div>
<div class="rd_box">
<div class="top"><i></i><h4>现在时间</h4><a class="more" href="http://www.24timemap.com/world">世界时间 ></a></div>
<div class="cont">
<b>中国，北京</b>
<em>2018年10月06日，星期六</em>
<div class="time" id="Clockk0"><span>19</span>:<span>45</span>:<span>56</span></div>
</div>
<div class="cont_b">当前时间为：晚上</div>
</div>
<div class="rd_box">
<div class="top"><i class="f1"></i><h4>日历查询</h4></div>
<div class="cont_jrbox1">
<p class="t1">2018年10月06日</p>
<p class="t2">星期六</p>
<p class="t3">2017生肖：狗年</p>
</div>
<div class="cont_jrbox2" style="height: 30px;">
<div class="form_w0">农历时间：</div>
<div class="form_w1">八月廿七戊戌年(狗年)辛酉月甲戌日</div>
<div class="form_w3"></div>
</div>
<div class="block10"></div>
<a href="" class="cal_display1" target="_blank"><span class="cal_m">2018/10</span><span class="cal_d">06</span></a>
<div class="crl"></div>
<div class="cont_b cont_b3"></div>
</div>
<div class="gg_r300">
<script>global_jx();</script>
</div>
<div class="block20"></div>
<div class="tabnav"><h3>常用城市</h3></div>
<div class="rowW">
<div class="row">
<div class="clocks"><a href="/usa/new-york" target="">
<div class="name"><b>纽约</b><span><img src="/upload/article/20170119/1484795966EjT7eE.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk1"><span class="hour">06</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
<div class="clocks"><a href="/australia/canberra" target="">
<div class="name"><b>堪培拉</b><span><img src="/upload/article/20170120/1484897692yGUzvj.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk2"><span class="hour">21</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
<div class="clocks"><a href="/france/paris" target="">
<div class="name"><b>巴黎</b><span><img src="/upload/article/20170120/1484889041qquQbP.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk3"><span class="hour">12</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
<div class="clocks"><a href="/japan/tokyo" target="">
<div class="name"><b>东京</b><span><img src="/upload/article/20170120/1484883573nm68Uj.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk4"><span class="hour">20</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
<div class="clocks"><a href="/china/beijing" target="">
<div class="name"><b>北京</b><span><img src="/upload/article/20170120/14848982802bzLhq.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk5"><span class="hour">19</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
<div class="clocks"><a href="/uk/london" target="">
<div class="name"><b>伦敦</b><span><img src="/upload/article/20170120/1484896748G9qCjs.png" width="24" height="20" /></span></div>
<div class="date">2018年10月06日</div>
<div class="time" id="Clockk6"><span class="hour">11</span>:<span class="minute">45</span>:<span class="second">56</span></div></a>
</div>
</div>
</div>
<div class="block20"></div>
<div class="tabnav"><h3>热门城市</h3></div>
<div class="row1">
<ul>
<li class="bg"><a href="/usa/midway-atoll" title="中途岛时间" target="_blank">中途岛</a> <i>星期六 00:45</i></li>
<li><a href="/singapore/sentosa" title="圣淘沙时间" target="_blank">圣淘沙</a> <i>星期六 19:45</i></li>
<li class="bg"><a href="/portugal/lisbon" title="里斯本时间" target="_blank">里斯本</a> <i>星期六 11:45</i></li>
<li><a href="/italy/venice" title="威尼斯时间" target="_blank">威尼斯</a> <i>星期六 12:45</i></li>
<li class="bg"><a href="/italy/rome" title="罗马时间" target="_blank">罗马</a> <i>星期六 12:45</i></li>
<li><a href="/germany/berlin" title="柏林时间" target="_blank">柏林</a> <i>星期六 12:45</i></li>
<li class="bg"><a href="/thailand/pattaya" title="芭提雅时间" target="_blank">芭提雅</a> <i>星期六 18:45</i></li>
<li><a href="/thailand/phuket" title="普吉岛时间" target="_blank">普吉岛</a> <i>星期六 18:45</i></li>
<li class="bg"><a href="/thailand/bangkok" title="曼谷时间" target="_blank">曼谷</a> <i>星期六 18:45</i></li>
<li><a href="/south-korea/jeju" title="济州岛时间" target="_blank">济州岛</a> <i>星期六 20:45</i></li>
<li class="bg"><a href="/south-korea/seoul" title="首尔时间" target="_blank">首尔</a> <i>星期六 20:45</i></li>
<li><a href="/japan/kyoto" title="京都时间" target="_blank">京都</a> <i>星期六 20:45</i></li>
<li class="bg"><a href="/china/shanghai" title="上海时间" target="_blank">上海</a> <i>星期六 19:45</i></li>
<li><a href="/brazil/sao-paulo" title="圣保罗时间" target="_blank">圣保罗</a> <i>星期六 08:45</i></li>
</ul>
</div>
<div class="block20"></div>
<div class="tabnav"><h3>热门国家</h3><p class="r"><a href="/world/asia" title="亚洲时间" target="_blank">亚洲</a> | <a href="/world/europe" target="_blank" title="欧洲时间">欧洲</a> | <a href="/world/namerica" target="_blank" title="北美洲时间">北美洲</a> | <a href="/world/samerica" target="_blank" title="南美洲时间">南美洲</a> | <a href="/world/australasia" target="_blank" title="大洋洲时间">大洋洲</a> | <a href="/world/africa" target="_blank" title="非洲时间">非洲</a></p></div>
<div class="row2">
<ul>
<li><a href="/switzerland" title="瑞士时间"><span><img src="/upload/article/20170120/1484896208bJBQv5.png" width="24" height="20"></span><b>瑞士</b></a></li>
<li><a href="/sweden" title="瑞典时间"><span><img src="/upload/article/20170120/14848961546BPqAC.png" width="24" height="20"></span><b>瑞典</b></a></li>
<li><a href="/spain" title="西班牙时间"><span><img src="/upload/article/20170120/1484896102z3A5zW.png" width="24" height="20"></span><b>西班牙</b></a></li>
<li><a href="/slovenia" title="斯洛文尼亚时间"><span><img src="/upload/article/20170120/1484896027shuJn7.png" width="24" height="20"></span><b>斯洛文尼亚</b></a></li>
<li><a href="/slovakia" title="斯洛伐克时间"><span><img src="/upload/article/20170120/1484895974q6LidN.png" width="24" height="20"></span><b>斯洛伐克</b></a></li>
<li><a href="/serbia" title="塞尔维亚时间"><span><img src="/upload/article/20170120/14848959253nyy4I.png" width="24" height="20"></span><b>塞尔维亚</b></a></li>
<li><a href="/san-marino" title="圣马力诺时间"><span><img src="/upload/article/20170120/148489587484CP9P.png" width="24" height="20"></span><b>圣马力诺</b></a></li>
<li><a href="/romania" title="罗马尼亚时间"><span><img src="/upload/article/20170120/14848883892ULHMe.png" width="24" height="20"></span><b>罗马尼亚</b></a></li>
<li><a href="/portugal" title="葡萄牙时间"><span><img src="/upload/article/20170120/1484895763SyKhjq.png" width="24" height="20"></span><b>葡萄牙</b></a></li>
<li><a href="/poland" title="波兰时间"><span><img src="/upload/article/20170120/1484895715mcvNbm.png" width="24" height="20"></span><b>波兰</b></a></li>
<li><a href="/norway" title="挪威时间"><span><img src="/upload/article/20170120/1484895666gmIETe.png" width="24" height="20"></span><b>挪威</b></a></li>
<li><a href="/montenegro" title="黑山时间"><span><img src="/upload/article/20170120/14848956132NVydh.png" width="24" height="20"></span><b>黑山</b></a></li>
<li><a href="/monaco" title="摩纳哥时间"><span><img src="/upload/article/20170120/14848955486R5JVF.png" width="24" height="20"></span><b>摩纳哥</b></a></li>
<li><a href="/luxembourg" title="卢森堡时间"><span><img src="/upload/article/20170120/1484895198deqssd.png" width="24" height="20"></span><b>卢森堡</b></a></li>
<li><a href="/lithuania" title="立陶宛时间"><span><img src="/upload/article/20170120/14848948846eGhxc.png" width="24" height="20"></span><b>立陶宛</b></a></li>
<li><a href="/liechtenstein" title="列支敦士登时间"><span><img src="/upload/article/20170120/14848948083GtEda.png" width="24" height="20"></span><b>列支敦士登</b></a></li>
<li><a href="/latvia" title="拉脱维亚时间"><span><img src="/upload/article/20170120/1484894603GuFURM.png" width="24" height="20"></span><b>拉脱维亚</b></a></li>
<li><a href="/kosovo" title="科索沃时间"><span><img src="/upload/article/20170120/1484894549i6fv7F.jpg" width="24" height="20"></span><b>科索沃</b></a></li>
<li><a href="/italy" title="意大利时间"><span><img src="/upload/article/20170120/148488922922zsIW.png" width="24" height="20"></span><b>意大利</b></a></li>
<li><a href="/ireland" title="爱尔兰时间"><span><img src="/upload/article/20170120/1484893924D6bShn.png" width="24" height="20"></span><b>爱尔兰</b></a></li>
<li><a href="/iceland" title="冰岛时间"><span><img src="/upload/article/20170120/1484893813Ts4PHD.png" width="24" height="20"></span><b>冰岛</b></a></li>
<li><a href="/hungary" title="匈牙利时间"><span><img src="/upload/article/20170120/1484893713Ax9rcQ.png" width="24" height="20"></span><b>匈牙利</b></a></li>
<li><a href="/greece" title="希腊时间"><span><img src="/upload/article/20170120/14848936457VxsIu.png" width="24" height="20"></span><b>希腊</b></a></li>
<li><a href="/germany" title="德国时间"><span><img src="/upload/article/20170120/1484884230P98R74.png" width="24" height="20"></span><b>德国</b></a></li>
<li><a href="/france" title="法国时间"><span><img src="/upload/article/20170120/1484889041qquQbP.png" width="24" height="20"></span><b>法国</b></a></li>
<li><a href="/finland" title="芬兰时间"><span><img src="/upload/article/20170120/1484893320axWRuW.png" width="24" height="20"></span><b>芬兰</b></a></li>
<li><a href="/denmark" title="丹麦时间"><span><img src="/upload/article/20170120/1484893040kvAImq.png" width="24" height="20"></span><b>丹麦</b></a></li>
<li><a href="/czech-republic" title="捷克时间"><span><img src="/upload/article/20170120/14848929923utfrH.png" width="24" height="20"></span><b>捷克</b></a></li>
<li><a href="/croatia" title="克罗地亚时间"><span><img src="/upload/article/20170120/1484892936fhNLrw.png" width="24" height="20"></span><b>克罗地亚</b></a></li>
<li><a href="/bosnia-herzegovina" title="波黑时间"><span><img src="/upload/article/20170120/1484892809KWA3Gp.png" width="24" height="20"></span><b>波黑</b></a></li>
<li><a href="/belgium" title="比利时时间"><span><img src="/upload/article/20170120/14848926808c5ptv.png" width="24" height="20"></span><b>比利时</b></a></li>
<li><a href="/belarus" title="白俄罗斯时间"><span><img src="/upload/article/20170120/14848926337Wjfdj.png" width="24" height="20"></span><b>白俄罗斯</b></a></li>
<li><a href="/austria" title="奥地利时间"><span><img src="/upload/article/20170120/1484892576bKRIhv.png" width="24" height="20"></span><b>奥地利</b></a></li>
<li><a href="/albania" title="阿尔巴尼亚时间"><span><img src="/upload/article/20170120/1484892469fyHGBV.png" width="24" height="20"></span><b>阿尔巴尼亚</b></a></li>
<li><a href="/palau" title="帕劳时间"><span><img src="/upload/article/20170120/1484897348W2xzRq.png" width="24" height="20"></span><b>帕劳</b></a></li>
<li><a href="/new-zealand" title="新西兰时间"><span><img src="/upload/article/20170120/1484897488KAavFJ.png" width="24" height="20"></span><b>新西兰</b></a></li>
<li><a href="/fiji" title="斐济时间"><span><img src="/upload/article/20170120/1484898030T9A5wA.png" width="24" height="20"></span><b>斐济</b></a></li>
<li><a href="/australia" title="澳大利亚时间"><span><img src="/upload/article/20170120/1484897692yGUzvj.png" width="24" height="20"></span><b>澳大利亚</b></a></li>
<li><a href="/zambia" title="赞比亚时间"><span><img src="/upload/article/20170119/1484803146iNmdNV.png" width="24" height="20"></span><b>赞比亚</b></a></li>
<li><a href="/sudan" title="苏丹时间"><span><img src="/upload/article/20170119/1484802828TPAwVU.png" width="24" height="20"></span><b>苏丹</b></a></li>
</ul>
</div>
</ul>
</div>
</div>
<div class="block10"></div>
<div class="links"> <em>友情链接</em>
<p>
<a href="http://www.24timemap.com/" target="_blank">时间网</a>
</p>
</div>
<div class="block20"></div>
</div>
<div class="footbg">
<div class="foot">
<p class="l">Copyright &copy; 2009-2017 时间地图网 . All Rights Reserved.<br /> 琼ICP备15000444号-4</p>
<p class="r">意见反馈 | 关于我们 | 广告联系 | 免责声明 | 商务合作 | 网站地图</p>
<div class="crl"></div>
</div>
<div style="display:none"><script language="javascript" src="http://www.24timemap.com/static/js/tongji.js"></script></div>
</div></body>
</html>
