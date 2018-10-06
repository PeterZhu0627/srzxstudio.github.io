
<!DOCTYPE HTML>
<!--suppress ALL -->
<html class="no-js" lang="zh-cmn-Hans">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
    <meta charset="UTF-8">
    <!--IE 8浏览器的页面渲染方式-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
    <!--默认使用极速内核：针对国内浏览器产商-->
    <meta name="renderer" content="webkit">
    <!--chrome Android 地址栏颜色-->
        <meta name="theme-color" content="#7266ba" />
    
    <meta http-equiv="x-dns-prefetch-control" content="on">
<link rel="dns-prefetch" href="//ws1.sinaimg.cn" />
<link rel="dns-prefetch" href="//api.live.bilibili.com" />
<link rel="dns-prefetch" href="//q.qlogo.cn" />
<link rel="dns-prefetch" href="//cdn.v2ex.com" />

    <title>[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法 - 神代綺凜の萌化小基地</title>
            <link rel="icon" type="image/ico" href="/favicon.ico">
        <meta name="description" content="本文比较适合初次尝试这样建站的萌新阅读，借助 GitHub Pages 平台，我们可以将自己的静态网站零成本托管到 GItHub，并且还可以使用自己的域名，甚至支持自动帮你申请 SSL 证书以开..." />
<meta name="keywords" content="windows,github,nodejs,ssl,hexo,https" />
<meta name="generator" content="Typecho 1.1/17.10.30" />
<meta name="template" content="handsome" />
<link rel="alternate" type="application/rss+xml" title="[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法 &raquo; 神代綺凜の萌化小基地 &raquo; RSS 2.0" href="https://lolico.moe/feed/tutorial/hexo-github-pages.html" />
<link rel="alternate" type="application/rdf+xml" title="[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法 &raquo; 神代綺凜の萌化小基地 &raquo; RSS 1.0" href="https://lolico.moe/feed/rss/tutorial/hexo-github-pages.html" />
<link rel="alternate" type="application/atom+xml" title="[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法 &raquo; 神代綺凜の萌化小基地 &raquo; ATOM 1.0" href="https://lolico.moe/feed/atom/tutorial/hexo-github-pages.html" />
<link rel="amphtml" href="https://lolico.moe/amp/tutorial/hexo-github-pages.html">
<link rel="miphtml" href="https://lolico.moe/mip/tutorial/hexo-github-pages.html">

        <!-- 第三方CDN加载CSS -->
        <link href="https://cdnjs.cat.net/ajax/libs/twitter-bootstrap/3.3.4/css/bootstrap.min.css" rel="stylesheet">


    <!-- 本地css静态资源 -->
    <link rel="stylesheet" href="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/css/function.min.css?v=4.4.020180702101" type="text/css" />
    <link rel="stylesheet" href="/usr/themes/handsome/assets/css/handsome.min.css?v=4.4.020180702101" type="text/css" />
    <link rel="stylesheet" href="/usr/themes/handsome/assets/css/handsome.css?v=1.3.4" type="text/css" />
    <!-- EditorMD -->
    <link rel="stylesheet" href="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/css/editormd.preview.min.mod.css?v=1.0.0">

    <!--主题组件css文件加载-->
    <link rel="stylesheet" href="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/css/features/jquery.fancybox.min.css?v=4.4.020180702101" type="text/css" />
        <link rel="stylesheet" href="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/css/features/code/vs.min.css?v=4.4.020180702101" type="text/css" />
    
    <!--引入英文字体文件-->
        <link rel="stylesheet" href="/usr/themes/handsome/assets/css/font.css?v=4.4.020180702101" type="text/css" />
    
    <style type="text/css">
        
        html.bg {
                   background-image:
               -moz-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -moz-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -moz-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -o-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -o-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -o-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -ms-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -ms-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -ms-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -webkit-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -webkit-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -webkit-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
               ;
        }
        .cool-transparent .off-screen+* .app-content-body {
                   background-image:
               -moz-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -moz-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -moz-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -o-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -o-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -o-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -ms-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -ms-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -ms-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
           ;
           background-image:
               -webkit-radial-gradient(-20% 140%, ellipse ,  rgba(143,192,193,.6) 30%,rgba(255,255,227,0) 50%),
               -webkit-radial-gradient(60% 40%,ellipse,   #d9e3e5 10%,rgba(44,70,76,.0) 60%),
               -webkit-linear-gradient(-45deg,  rgba(143,181,158,.8) -10%,rgba(213,232,211,.8) 80% )
               ;
        }.wrapper-md>#comments{overflow:visible!important}
.preview .post-inser{background: rgba(255,255,255,.6);transition:all .3s}
.preview .post-inser:hover{background: rgba(255,255,255,1)}
.all-inline .block-img{display:inline}
.all-inline{word-break:break-all!important}
.pointer-cursor{cursor: pointer}    </style>

    <!--全站jquery-->
    <script src="https://cdnjs.cat.net/ajax/libs/jquery/2.2.4/jquery.min.js"></script>

    <!--网站统计代码-->
    <!-- font-awesome -->
<link href="https://cdnjs.loli.net/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">

</head>

<body id="body">
    <div id="alllayout" class="app app-aside-fixed app-header-fixed ">    <!-- header -->
        <div id="bg"></div>
  <header id="header" class="app-header navbar" role="menu">
      <!-- navbar header（交集处） -->
        <div class="navbar-header bg-primary">
        <button class="pull-right visible-xs dk" ui-toggle-class="show animated animated-lento fadeIn" target=".navbar-collapse">
          <i class="fontello fontello-gear text-lg"></i>
        </button>
        <button class="pull-right visible-xs" ui-toggle-class="off-screen animated" target=".app-aside" ui-scroll="app">
          <i class="fontello fontello-menu text-lg"></i>
        </button>
        <!-- brand -->
        <a href="https://lolico.moe/" class="navbar-brand text-lt">
                                                <i class="fontello fontello-home"></i>
                                <span class="hidden-folded m-l-xs">LOLI! NEKO!</span>
                    </a>
        <!-- / brand -->
      </div>
      <!-- / navbar header -->

      <!-- navbar collapse（顶部导航栏） -->
    <div class="collapse pos-rlt navbar-collapse box-shadow bg-primary">        <!-- buttons -->
        <div class="nav navbar-nav hidden-xs">
          <a id="aside-btn" href="#" class="btn no-shadow navbar-btn" ui-toggle-class="app-aside-folded" target=".app">
            <i class="fontello fontello-dedent text icon-fw"></i>
            <i class="fontello fontello-indent icon-fw text-active"></i>
          </a>
          <a href="#" class="btn no-shadow navbar-btn" ui-toggle-class="show" target="#aside-user">
            <i class="iconfont icon-user icon-fw"></i>
          </a>
        </div>
        <!-- / buttons -->


        <!-- search form -->
        <form id="searchform" class="navbar-form navbar-form-sm navbar-left shift" method="post" role="search">
          <div class="form-group">
            <div class="input-group rounded bg-light">
              <input id="search_input" type="search" name="s" class="transparent rounded form-control input-sm no-border padder" required placeholder="输入关键词搜索…">
              <span id="search_submit" class="transparent input-group-btn">
                  <button  type="submit" class="transparent btn btn-sm"><i class="fontello fontello-search"></i></button>
              </span>
            </div>
          </div>
        </form>
          <a href="" style="display: none" id="searchUrl"></a>
        <!-- / search form -->
                <ul class="nav navbar-nav navbar-right">
                        <li class="dropdown"><a target="_self" href="https://lolico.moe/cross.html" class="dropdown-toggle"><i class="fa fa-user icon-fw"></i><span class="visible-xs-inline">关于我</span></a></li><li class="dropdown"><a target="_self" href="https://lolico.moe/contact.html" class="dropdown-toggle"><i class="fa fa-phone icon-fw"></i><span class="visible-xs-inline">联系我</span></a></li>                      <!--闲言碎语-->
          <li class="dropdown">
            <a href="#" data-toggle="dropdown" class="dropdown-toggle">
              <i class="fontello fontello-bell icon-fw"></i>
              <span class="visible-xs-inline">
              闲言碎语              </span>
              <span class="badge badge-sm up bg-danger pull-right-xs"></span>
            </a>
            <!-- dropdown -->
            <div class="dropdown-menu w-xl animated fadeInUp">
              <div class="panel bg-white">
                <div class="panel-heading b-light bg-light">
                  <strong>
              闲言碎语                  </strong>
                </div>
                <div class="list-group" id="smallRecording">
                  <a href="https://lolico.moe/index.php/cross.html" class="list-group-item"><span class="clear block m-b-none words_contents">把公主链接下回来了（真香<br><small class="text-muted">2018-7-3 15:38:23</small></span></a><a href="https://lolico.moe/index.php/cross.html" class="list-group-item"><span class="clear block m-b-none words_contents">退坑公主链接，回坑碧蓝航线。真的，公主链接这样的游戏，是不会带来快乐的。<br><small class="text-muted">2018-6-3 22:45:37</small></span></a><a href="https://lolico.moe/index.php/cross.html" class="list-group-item"><span class="clear block m-b-none words_contents">今天 Steam 收到了Lise·Hohenstein送的 fault - milestone 两部，超开心的，从来没想过会有人送什么东西之类的，心情难以言表……<br><small class="text-muted">2018-3-28 22:52:58</small></span></a>                </div>
              </div>
            </div>
          </li>
          <!--/闲言碎语-->
                                  <!--登录管理-->
          <li class="dropdown" id="easyLogin">
            <a onclick="return false" data-toggle="dropdown" class="dropdown-toggle clear" data-toggle="dropdown">
                        <span class="text">登录</span>
                        <b class="caret"></b><!--下三角符号-->
            </a>
            <!-- dropdown(已经登录) -->
                      <div class="dropdown-menu w-lg wrapper bg-white" aria-labelledby="navbar-login-dropdown">
            <form id="Login_form" action="https://lolico.moe/index.php/action/login?_=880878ad57f1fdac3d112e76129efcdb" method="post">
              <div class="form-group">
                <label for="navbar-login-user">用户名</label>
                <input type="text" name="name" id="navbar-login-user" class="form-control" placeholder="用户名或电子邮箱"></div>
              <div class="form-group">
                <label for="navbar-login-password">密码</label>
                <input type="password" name="password" id="navbar-login-password" class="form-control" placeholder="密码"></div>
              <button type="submit" id="login-submit" name ="submitLogin" class="btn btn-block btn-primary">
              <span class="text">登录</span>
              <span class="text-active">登录中...</span>
                  <span class="banLogin_text">刷新页面后登录</span>
              <i class="animate-spin  fontello fontello-spinner hide" id="spin-login"></i>
                  <i class="animate-spin fontello fontello-refresh hide" id="ban-login"></i>
              </button>
              
              <input type="hidden" name="referer" value="https://lolico.moe"
                     data-current-url="value"></form>
          </div>
                    </li>
          <!--/登录管理-->
                    </ul>
      </div>
      <!-- / navbar collapse -->
  </header>
    <!-- / header -->
	<!-- aside -->
	    <!--选择侧边栏的颜色-->
  <aside id="aside" class="app-aside hidden-xs bg-dark">  <!--<aside>-->
      <div class="aside-wrap">
        <div class="navi-wrap">
          <!-- user -->
          <div class="clearfix hidden-xs text-center hide  show" id="aside-user">
            <div class="dropdown wrapper">
                <div ui-nav>
                          <a href="https://lolico.moe/cross.html">
                            <span class="thumb-lg w-auto-folded avatar m-t-sm">
                  <img src="/usr/img/avatar1.png" class="img-full">
                </span>
              </a>
                </div>
              <a href="#" data-toggle="dropdown" class="dropdown-toggle hidden-folded">
                <span class="clear">
                  <span class="block m-t-sm">
                    <strong class="font-bold text-lt">神代綺凜</strong>
                    <b class="caret"></b>
                  </span>
                  <span class="text-muted text-xs block">ななひら天下第一！</span>
                </span>
              </a>
              <!-- dropdown -->
              <ul class="dropdown-menu animated fadeInRight w hidden-folded">
                <li class="wrapper b-b m-b-sm bg-info m-t-n-xs">
                  <span class="arrow top hidden-folded arrow-info"></span>
                  <div>
                                                <p>睡你麻痹起来嗨</p>
                                  </div>
                  <div class="progress progress-xs m-b-none dker">
                    <div class="progress-bar bg-white" data-toggle="tooltip" data-original-title="时间已经度过79.17%" style="width: 79.17%"></div>
                  </div>
                </li>
              <!--文章RSS订阅-->
              <li>
                <a href="https://lolico.moe/feed/" data-toggle="tooltip" title="订阅文章 Feed 源">
                  <i style="position: relative;width: 30px;margin: -11px -10px;margin-right: 0px;overflow: hidden;line-height: 30px;text-align: center;" class="fontello fontello-rss" ></i><span>文章RSS</span>
                </a>
              </li>
              <!--评论RSS订阅-->
              <li>
                <a href="https://lolico.moe/feed/comments/" data-toggle="tooltip" title="订阅评论 Feed 源"><i style="position: relative;width: 30px;margin: -11px -10px;margin-right: 0px;overflow: hidden;line-height: 30px;text-align: center;" class="fontello fontello-rss-square" ></i><span>评论RSS</span></a>
              </li>
              <!--哔哩哔哩RSS订阅-->
              <li>
                <a href="https://rsshub.app/bilibili/user/video/901801" data-toggle="tooltip" title="订阅哔哩哔哩 Feed 源" target="_blank">
                  <i style="position: relative;width: 30px;margin: -11px -10px;margin-right: 0px;overflow: hidden;line-height: 30px;text-align: center;" class="fa fa-rss" ></i><span>哔哩哔哩RSS</span>
                </a>
              </li>
              <li>
                <a href="https://rsshub.app/bilibili/live/room/3806710" data-toggle="tooltip" title="订阅哔哩哔哩直播开播 Feed 源" target="_blank">
                  <i style="position: relative;width: 30px;margin: -11px -10px;margin-right: 0px;overflow: hidden;line-height: 30px;text-align: center;" class="fa fa-rss" ></i><span>哔哩哔哩直播开播RSS</span>
                </a>
              </li>
              <li class="divider"></li>
                                              <li>
                <a href="https://lolico.moe/admin/login.php">登录</a>
              </li>
                                              </ul>
              <!-- / dropdown -->
            </div>
            <div class="line dk hidden-folded"></div>
          </div>
          <!-- / user -->

          <!-- nav -->
          <nav ui-nav class="navi clearfix">
            <ul class="nav">
             <!--index-->
              <li class="hidden-folded padder m-t m-b-sm text-muted text-xs">
                <span>导航</span>
              </li>
                                          <!--主页-->
              <li>
                <a href="https://lolico.moe/" class="auto">
                  <i class="iconfont icon-zhuye icon text-md"></i>
                  <span>首页</span>
                </a>
              </li>
              <!-- /主页 -->
                            <!-- TG -->
              <li>
                <a href="https://t.me/kirin_no_manimani" class="auto" target="_blank">
                  <i class="fa fa-telegram icon text-md"></i>
                  <span>TG 频道</span>
                </a>
              </li>
              <!-- 直播 -->
              <li id="bilibili-live" class="hide">
                  <a target="_blank" href="http://live.bilibili.com/3806710" class="auto">
                      <i class="fa fa-play-circle icon text-md"></i>
                      <span>哔哩哔哩~直播中</span>
                  </a>
              </li>
              <!-- /直播 -->
              <li class="">
                <a data-no-instant="" class="auto">
                  <span class="pull-right text-muted">
                    <i class="fa icon-fw fa-angle-right text"></i>
                    <i class="fa icon-fw fa-angle-down text-active"></i>
                  </span>
                  <i class="fa fa-wrench"></i>
                  <span>嗯？</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant="">
                      <span>嗯？</span>
                    </a>
                  </li>
                  <li> <a target="_self" href="https://lolico.moe/kms.html" class ="auto"><i class="fa fa-key icon text-md"></i><span>KMS 激活</span></a></li><li> <a target="_blank" href="https://yww.uy" class ="auto"><i class="fa fa-link icon text-md"></i><span>爽链接</span></a></li><li> <a target="_blank" href="https://osusig.lolico.moe" class ="auto"><i class="fa fa-circle icon text-md"></i><span>osu!sig</span></a></li><li> <a target="_blank" href="https://img.lolico.moe" class ="auto"><i class="fa fa-picture-o icon text-md"></i><span>萌图库</span></a></li><li> <a target="_blank" href="https://files.lolico.moe" class ="auto"><i class="fa fa-gift icon text-md"></i><span>小玩意</span></a></li>				</ul>
              </li>
                              <li class="line dk"></li>
			<!--Components-->
              <li class="hidden-folded padder m-t m-b-sm text-muted text-xs">
                <span>组成</span>
              </li>
              <!--萌化项目-->
              <li>
                <a data-no-instant class="auto">
                  <span class="pull-right text-muted">
                    <i class="fa icon-fw fa-angle-right text"></i>
                    <i class="fa icon-fw fa-angle-down text-active"></i>
                  </span>
                  <i class="fa fa-paw"></i>
                  <span>萌化项目</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant>
                      <span>萌化项目</span>
                    </a>
                  </li><!--这个字段不会被显示出来-->
                  <!--循环输出萌化项目-->
                  <li><a href='https://lolico.moe/moe-project/bilibili-nekopara.html'><span>[Bilibili-Style] 哔哩哔哩 Nekopara B站网页萌化主题</span></a></li><li><a href='https://lolico.moe/moe-project/ps2017-fu.html'><span>[Photoshop CC 2017] 启动界面萌化</span></a></li><li><a href='https://lolico.moe/moe-project/osu-nekopara.html'><span>[osu] Nekopara V3.1</span></a></li><li><a href='https://lolico.moe/moe-project/baidu-moe.html'><span>[Stylish] 百度萌化样式</span></a></li><li><a href='https://lolico.moe/moe-project/we-okita-souji.html'><span>[Wallpaper Engine 动态壁纸] FGO - 沖田総司 飘雪 1080P(waifu2x) 60fps</span></a></li>                </ul>
              </li>
              <!--个人项目-->
              <li>
                <a data-no-instant class="auto">
                  <span class="pull-right text-muted">
                    <i class="fa icon-fw fa-angle-right text"></i>
                    <i class="fa icon-fw fa-angle-down text-active"></i>
                  </span>
                  <i class="fa fa-github"></i>
                  <span>个人项目</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant>
                      <span>个人项目</span>
                    </a>
                  </li><!--这个字段不会被显示出来-->
                  <!--循环输出个人项目-->
                  <li><a href='https://lolico.moe/projects/bilibili-orig-img.html'><span>[Bilibili] 使新版动态图片能够查看原图</span></a></li><li><a href='https://lolico.moe/projects/pxder.html'><span>[Pxder] Pixiv 插画下载器</span></a></li><li><a href='https://lolico.moe/projects/qq-robot-picfinder.html'><span>[开源] 二次元搜图QQ机器人</span></a></li><li><a href='https://lolico.moe/projects/block-countries-ips.html'><span>[不再维护] 屏蔽任意一个国家所有IP的一键脚本</span></a></li><li><a href='https://lolico.moe/projects/sc-private-letter.html'><span>[SC private letter] 一个基于 serverchan 微信推送服务的私信发送站</span></a></li><li><a href='https://lolico.moe/technology/comment2wechat.html'><span>[Typecho插件] 新评论微信提醒 Comment2Wechat V2.0</span></a></li><li><a href='https://lolico.moe/technology/nhentai-downloader.html'><span>[Shell] nhentai一键批量下载</span></a></li>                </ul>
              </li>
              <!--分类category-->
              <li>
                <a class="auto">
                  <span class="pull-right text-muted">
                    <i class="fontello icon-fw fontello-angle-right text"></i>
                    <i class="fontello icon-fw fontello-angle-down text-active"></i>
                  </span>
                  <i class="glyphicon glyphicon-th"></i>
                  <span>分类</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant>
                      <span>分类</span>
                    </a>
                  </li>
                  <!--循环输出分类-->
                    <li><a href="https://lolico.moe/gotagota"><b class="badge pull-right">13</b><span>杂七杂八的</span></a></li><li><a href="https://lolico.moe/yoimono"><b class="badge pull-right">20</b><span>好东西就应该分享出来</span></a></li><li><a href="https://lolico.moe/tutorial"><b class="badge pull-right">18</b><span>教程</span></a></li><li><a href="https://lolico.moe/software"><b class="badge pull-right">7</b><span>小众软件</span></a></li><li><a class="auto"><span class="pull-right text-muted">
                    <i class="fontello icon-fw fontello-angle-right text"></i>
                    <i class="fontello icon-fw fontello-angle-down text-active"></i>
                  </span><span>技术？不存在的</span></a><ul class="nav nav-sub dk child-nav"><li><a href="https://lolico.moe/technology"><b class="badge pull-right">8</b><span>技术？不存在的</span></a></li><li><a href="https://lolico.moe/modification"><b class="badge pull-right">3</b><span>各种魔改</span></a></li></ul></li><li><a href="https://lolico.moe/moe-project"><b class="badge pull-right">5</b><span>萌化项目</span></a></li><li><a href="https://lolico.moe/projects"><b class="badge pull-right">7</b><span>个人项目</span></a></li><li><a href="https://lolico.moe/linux-memo"><b class="badge pull-right">10</b><span>Linux 笔记</span></a></li><li><a href="https://lolico.moe/java"><b class="badge pull-right">1</b><span>Java 笔记</span></a></li><li><a href="https://lolico.moe/nodejs-memo"><b class="badge pull-right">2</b><span>Node.js 笔记</span></a></li><li><a href="https://lolico.moe/vps-domain"><b class="badge pull-right">6</b><span>域名 & VPS</span></a></li><li><a href="https://lolico.moe/resource"><b class="badge pull-right">2</b><span>资源分享</span></a></li>                </ul>
              </li>
              <!--独立页面pages-->
              <li>
                <a class="auto">
                  <span class="pull-right text-muted">
                    <i class="fontello icon-fw fontello-angle-right text"></i>
                    <i class="fontello icon-fw fontello-angle-down text-active"></i>
                  </span>
                  <i class="glyphicon glyphicon-file"></i>
                  <span>页面</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant>
                      <span>页面</span>
                    </a>
                  </li><!--这个字段不会被显示出来-->
                  <!--循环输出独立页面-->
                                                                                   <li><a href="https://lolico.moe/links.html"><span>友情链接</span></a></li>
                                                                 <li><a href="https://lolico.moe/archive.html"><span>文章归档</span></a></li>
                                                                 <li><a href="https://lolico.moe/cross.html"><span>关于我</span></a></li>
                                                                 <li><a href="https://lolico.moe/contact.html"><span>留言板</span></a></li>
                                   </ul>
              </li>
              <!--友情链接-->
              <li>
                <a class="auto">
                  <span class="pull-right text-muted">
                    <i class="fontello icon-fw fontello-angle-right text"></i>
                    <i class="fontello icon-fw fontello-angle-down text-active"></i>
                  </span>
                  <i class="iconfont icon-links"></i>
                  <span>友链</span>
                </a>
                <ul class="nav nav-sub dk">
                  <li class="nav-sub-header">
                    <a data-no-instant>
                      <span>友链</span>
                    </a>
                  </li>
                  <!--使用links插件，输出全站友链-->
                 <li><a href="https://www.moerats.com/" target="_blank" title="Rat的博客"><span>MoeRats</span></a></li><li><a href="https://2cywiki.com/" target="_blank" title="聚合galgame与动漫资源"><span>二次元百科</span></a></li><li><a href="https://saigaocy.cc" target="_blank" title="美好二次元从这里开始"><span>赛高次元社</span></a></li><li><a href="https://affman.tw" target="_blank" title="分享不止于此"><span>Suzume</span></a></li><li><a href="https://sfz.one/" target="_blank" title="rt"><span>宅男次元社</span></a></li><li><a href="https://ykhut.com" target="_blank" title="夜空酱的博客"><span>夜空酱</span></a></li><li><a href="https://blog.ilemonrain.com/" target="_blank" title="生活 | 技术 | 音乐 | 随笔"><span>极光星空</span></a></li><li><a href="https://sometimesnaive.org" target="_blank" title="南琴浪的博客"><span>南琴浪</span></a></li><li><a href="https://mikuac.com" target="_blank" title="SimpleZero的博客"><span>SimpleZero</span></a></li><li><a href="https://www.54yt.net" target="_blank" title="追尋真正的生活"><span>神楽坂 玉兔</span></a></li><li><a href="https://typecho.linyezhandidi.com/" target="_blank" title="林叶展的博客"><span>林叶展弟弟</span></a></li><li><a href="https://www.94ish.me/" target="_blank" title="千影的博客"><span>就是爱生活</span></a></li><li><a href="https://dcc.cat/" target="_blank" title="网络安全大佬（给大佬递茶"><span>DCC的小窝</span></a></li><li><a href="https://www.wikimoe.com/" target="_blank" title="很萌的二次元WIKI"><span>维基萌</span></a></li><li><a href="https://52huameng.com/" target="_blank" title="一名热爱ACGN文化的高中Coder"><span>华梦</span></a></li><li><a href="https://muz1.xyz" target="_blank" title="技术、随笔"><span>neverland</span></a></li><li><a href="http://saltfish.vip" target="_blank" title="临渊羡鱼，不如退而结网——其实是咸鱼笔记......"><span>羡渔笔记</span></a></li><li><a href="http://nlyx.fun/" target="_blank" title="每时每刻都在搞事情的博客"><span>南楼月下</span></a></li><li><a href="http://blog.gz528.com" target="_blank" title="九月丶的个人技术博客"><span>九月丶</span></a></li>                </ul>
              </li>
                            </ul>
          </nav>
          <!-- nav -->
        </div><!--.navi-wrap-->
        <a><img src="/usr/img/kotori.png" id="kotori" class="hidekotori" data-toggle="tooltip" data-placement="right" data-original-title="返回顶部" style="z-index:10000"></a>
      </div><!--.aside-wrap-->
  </aside>
<!-- content -->
<div id="content" class="app-content">
	<!-- / aside -->

<!-- <div id="content" class="app-content"> -->
        <div id="loadingbar" class="butterbar hide">
            <span class="bar"></span>
        </div>
   <a class="off-screen-toggle hide"></a>
   <main class="app-content-body ">
    <div class="hbox hbox-auto-xs hbox-auto-sm">
    <!--文章-->
     <div class="col center-part">
         <!--生成分享图片必须的HTML结构-->
                 <style>
        
        .mdx-si-head .cover{
            object-fit: cover;
            width: 100%;
            height: 100%
        }
        
</style>
<div class="mdx-share-img" id="mdx-share-img"><div class="mdx-si-head" style="background-image:url(https://blog-1257171214.file.myqcloud.com/usr/uploads/2018/05/2578777832.jpg)"><p>神代綺凜</p><span>[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法</span></div><div 
class="mdx-si-sum">本文比较适合初次尝试这样建站的萌新阅读，借助 GitHub Pages 平台，我们可以将自己的静态网站零成本托管到...</div><div class="mdx-si-box"><span>扫描右侧二维码阅读全文</span><div class="mdx-si-qr" id="mdx-si-qr"><img 
src="https://lolico.moe/usr/themes/handsome/libs/GetCode.php?type=url&content=https://lolico.moe/tutorial/hexo-github-pages.html"></div></div><div class="mdx-si-time">29<br><span 
class="mdx-si-time-2">2018/05</span></div></div>    <!--标题下的一排功能信息图标：作者/时间/浏览次数/评论数/分类-->
      
        <header id="small_widgets" class="bg-light lter b-b wrapper-md">
             <h1 class="entry-title m-n font-thin h3 text-black l-h">[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法</h1>       <!--文章标题下面的小部件-->
                  <ul  class="entry-meta text-muted list-inline m-b-none small
             post-head-icon">
             <!--作者-->
             <li class="meta-author"><i class="fontello fontello-user" aria-hidden="true"></i><span class="sr-only">魔改症末期患者：</span> <a class="meta-value" href="https://lolico.moe/author/1/" rel="author"> 神代綺凜</a></li>
             <!--发布时间-->
             <li class="meta-date"><i class="fontello fontello-clock-o" aria-hidden="true"></i>&nbsp;<span class="sr-only">发布时间：</span><time class="meta-value">2018 年 05 月 29 日</time></li>
             <!--浏览数-->
             <li class="meta-views"><i class="fontello fontello-eye" aria-hidden="true"></i>&nbsp;<span class="meta-value">3128&nbsp;次浏览</span></li>
                              <!--评论数-->
                 <li class="meta-comments"><i class="iconfont icon-comments-o" aria-hidden="true"></i>&nbsp;<a
                             class="meta-value" href="#comments">&nbsp;14 条评论</a></li>
                          <!--文字数目-->
             <li class="meta-word"><i class="fontello fontello-pencil"></i>&nbsp;<span class="meta-value">2237&nbsp;字数</span></li>
             <!--分类-->
             <li class="meta-categories"><i class="fontello fontello-tags" aria-hidden="true"></i> <span class="sr-only">分类：</span> <span class="meta-value"><a href="https://lolico.moe/tutorial">教程</a></span></li>
         </ul>
      </header>
      <div class="wrapper-md" id="post-panel">
	   <ol class="breadcrumb bg-white b-a" itemscope=""><li>
                 <a href="https://lolico.moe/" itemprop="breadcrumb" title="返回首页" data-toggle="tooltip"><i class="fontello fontello-home" aria-hidden="true"></i>&nbsp;首页</a>
             </li><li class="active">正文&nbsp;&nbsp;</li>
              <div style="float:right;">
   分享到：
   <style>
   i.iconfont.icon-qzone:after {
    padding: 0 0 0 5px;
    color: #ccc;
    content: "/\00a0";
    }
    
   </style>
   <a href="http://sns.qzone.qq.com/cgi-bin/qzshare/cgi_qzshare_onekey?url=https://lolico.moe/tutorial/hexo-github-pages.html&title=[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法&site=https://lolico.moe/" itemprop="breadcrumb" target="_blank" title="" data-toggle="tooltip" data-original-title="分享到QQ空间" onclick="window.open(this.href, 'qzone-share', 'width=550,height=335');return false;"><i style ="font-size:15px;" class="iconfont icon-qzone" aria-hidden="true"></i></a>
   <a href="http://service.weibo.com/share/share.php?url=https://lolico.moe/tutorial/hexo-github-pages.html&title=[Hexo + GitHub Pages] 零成本的 HTTPS 建站大法" target="_blank" itemprop="breadcrumb" title="" data-toggle="tooltip" data-original-title="分享到微博" onclick="window.open(this.href, 'weibo-share', 'width=550,height=335');return false;"><i style ="font-size:15px;" class="fontello fontello-weibo" aria-hidden="true"></i></a></div></ol>       <!--博客文章样式 begin with .blog-post-->
       <div id="postpage" class="blog-post">
        <article class="panel">
        <!--文章页面的头图-->
        <div class="entry-thumbnail" aria-hidden="true"><div class="item-thumb lazy" data-original="https://blog-1257171214.file.myqcloud.com/usr/uploads/2018/05/2578777832.jpg" style="background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)"></div></div>         <!--文章内容-->
         <div id="post-content" class="wrapper-lg">
          <div class="entry-content l-h-2x editormd-html-preview">
          <p>本文比较适合初次尝试这样建站的萌新阅读，借助 GitHub Pages 平台，我们可以将自己的静态网站<strong>零成本</strong>托管到 GItHub，并且还可以使用自己的域名，甚至支持自动帮你申请 SSL 证书以开启 HTTPS 访问，可以说是非常造福射惠了~<!--more--></p>
<p>Head Pic: <a href="https://www.pixiv.net/member_illust.php?mode=medium&amp;illust_id=64035231" title="「そらたび」/「凪白みと」[pixiv]">「そらたび」/「凪白みと」[pixiv]</a></p>
<h1>GitHub Pages</h1>
<p>2018年5月1日，GitHub 正式宣布 GitHub Pages (*.github.io) 支持自定义域名 HTTPS，可以自动帮你申请 Let's Encrypt 的 SSL 证书并自动部署、续期，这就非常劲爆了</p>
<p>这意味着你可以不用花钱去租赁主机，仅仅需要购买一个域名（如果你愿意使用 GitHub 给的 *.github.io 域名，那甚至连域名钱都不用花了），就可以享受到建站到 SSL 的全套服务，而且访问速度也不赖</p>
<p>当然，只限纯静态网站（仅 html + css + js），关于这个，我仅知道也只能推荐 <a href="https://hexo.io/zh-cn/" target="_blank">Hexo</a>，用的人也蛮多的</p>
<h2>前言</h2>
<p>本文属于启蒙型文章，因为我不用 Hexo，所以我没办法写出更深层次的教程。主要目的还是为了介绍 GitHub Pages 的 HTTPS 要点，Hexo 算是附赠的（什么鬼</p>
<p>我会推荐写得好的 Hexo 搭建教程文章，并补充一些关键点，以及说明 GitHub Pages 的建立。</p>
<h2>GitHub Pages 的建立</h2>
<p>如果你没有 GitHub 帐号那当然得注册，进入首页后点击右上角加号，“New repository”</p>
<p>接下来是很关键的一点，<strong>Name 必须填写成<code>yourname.github.io</code>的形式</strong>，将<code>yourname</code>替换成你的用户名，例如下图中我自己的账户的用户名是<code>ykilin</code></p>
<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=" data-original="https://blog-1257171214.file.myqcloud.com/usr/uploads/2018/05/1342732500.png" alt=""  /></p>
<p>接着，进入新建好的项目页面，点击右侧的“Setting”进入设置页面</p>
<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=" data-original="https://blog-1257171214.file.myqcloud.com/usr/uploads/2018/05/4270532664.png" alt=""  /></p>
<p>往下拉找到“GitHub Pages”，将其开启，然后你就可以在“Custom domain”中填入你自己的域名了，记得点“Save”</p>
<p>以下是注意点：</p>
<ol>
<li>设置好之后，请为你填写的那个自定义域名创建 CNAME 记录，指向<code>yourname.github.io</code>（将<code>yourname</code>替换成你的用户名）</li>
<li>勾选“Enforce HTTPS”即可以开启我在文章开头提到的“GitHub Pages 支持自定义域名 HTTPS”啦！<br />
不过如果你是刚设置好自定义域名，这个选项应该是灰色的，因为你的自定义域名的 CNAME 记录并没不会那么快生效<br />
你需要做的仅仅是等待，一般短则几十分钟长则几个小时，等 GitHub 认为你的解析生效了，这个勾就可以勾上了</li>
</ol>
<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=" data-original="https://blog-1257171214.file.myqcloud.com/usr/uploads/2018/05/963883469.png" alt=""  /></p>
<p>然后你可以试着访问一下你的自定义域名，应该就有 HTTPS 并且会显示 GitHub Pages 默认页了</p>
<h2>关于 Hexo</h2>
<p>Hexo 是一个快速、简洁且高效的博客框架，使用 Markdown（或其他渲染引擎）解析文章。</p>
<p>由于是基于 Node.js，使用上（例如新建文章）依靠命令行完成，因此如果你有编程语言基础会上手的比较快。对于纯萌新……感觉是不太好起步……</p>
<h3>准备工作</h3>
<p>*这些都是对于 Windows 的</p>
<h4>Node.js</h4>
<p>首先需要安装 Node.js，到官网 <a href="https://nodejs.org/" target="_blank">https://nodejs.org/</a> ，点击左侧的绿色按钮下载安装包并安装即可。</p>
<p>安装过程中“Custom Setup”有一个选项是要不要添加到系统环境变量（英文，注意一下有没有“<strong>Add to PATH</strong>”这个单词），一定要选</p>
<h3>Git</h3>
<p>直接去 Git 官网下载 <a href="https://git-scm.com/download/win" target="_blank">https://git-scm.com/download/win</a></p>
<p>安装步骤及环境变量设置请参考 <a href="https://www.jianshu.com/p/fee5baf756c8" target="_blank">windows安装git和环境变量配置</a></p>
<h2>Hexo 的使用</h2>
<p>推荐以下几篇文章，请注意，你需要做的是参考、理解、根据你的实际需要效仿，而不是完全照搬步骤</p>
<ol>
<li><a href="https://blog.csdn.net/gdutxiaoxu/article/details/53576018" target="_blank">手把手教你用 Hexo+Github 搭建属于自己的博客</a></li>
<li><a href="https://www.jianshu.com/p/3e6083a2b498" target="_blank">Hexo配合github搭建网站</a></li>
<li><a href="https://www.jianshu.com/p/e03e363713f9" target="_blank">通过Git将Hexo博客部署到服务器</a></li>
</ol><hr class="content-copyright" style="margin-top:50px" /><blockquote class="content-copyright" style="font-style:normal"><p class="content-copyright">版权声明：本文为原创文章，版权归 <a href="https://lolico.moe/" target="_blank">神代綺凜</a> 所有。</p><p class="content-copyright">本文链接：<a class="content-copyright" href="https://lolico.moe/tutorial/hexo-github-pages.html">https://lolico.moe/tutorial/hexo-github-pages.html</a></p><p class="content-copyright">所有原创文章采用 <a href="https://creativecommons.org/licenses/by-nc/4.0/deed.zh" target="_blank">知识共享署名-非商业性使用 4.0 国际许可协议</a> 进行许可。<br>您可以自由的转载和修改，但请务必注明文章来源并且不可用于商业目的。</p></blockquote>          </div>
                              <!--文章页脚的广告位-->
                 <div style="margin-top:20px;text-align:center">
<p style="font-size:14px">搬瓦工VPS优惠套餐又又又补货啦，建站稳如狗，支持支付宝，循环出账94折优惠码<code>BWH26FXH3HIQ</code>
<br>①年付仅需<code>$18</code>电信联通直连的亚洲优化线路，1核/512M内存/10G硬盘/1000GB@1Gbps【<a href="/link/bwg18" target="_blank"><span style="color:red">点击购买</span></a>】
<br>②年付<code>$18</code>的可换成<code>CN2</code>线路（流量会变为<code>180G</code>），1核/512M内存/10G硬盘/500GB@1Gbps【<a href="/link/bwg18cn2" target="_blank"><span style="color:red">点击购买</span></a>】
<br>③年付<code>$28</code>的电信<code>CN2</code>联通直连线路，1核/512M内存/10G硬盘/500GB@1Gbps【<a href="/link/bwg28" target="_blank"><span style="color:red">点击购买</span></a>】（购买后请到后台切<code>DC8</code>机房以获得最佳体验）</p>
<div class="endad" style="text-align:center;font-weight:bold">
	<style type="text/css">
		#endadtb{margin:auto!important;max-width:486px}
		.endad img{cursor:default!important}
		.endadtr{background-color:transparent!important;border:none!important}
		.endadtd{border:none!important;padding:0!important}
		.endad i:before{font-size:50px}
		.endad .table-responsive{margin:0!important;border:none!important}
	</style>
	<span style="font-size:34px">我的文章对您有帮助吗？</span><br>
	<div style="margin-top:-13px"><del style="font-size:14px">我很可爱 请给我钱</del></div>
	<table id="endadtb">
		<tr class="endadtr">
			<td class="endadtd" width="50%"><img nogallery src="/usr/img/pay/zfbhb.png"></td>
			<td class="endadtd"><i class="fa fa-arrow-right" aria-hidden="true" style="color:red"></i></td>
			<td class="endadtd" width="50%"><img nogallery src="/usr/img/pay/alipay.gif"></td>
		</tr>
	</table>
	<span style="font-size:18px">扫一扫拿红包 → 扫商家收款码 → 转账与红包相等的金额</span><br>
	<span style="font-size:20px;color:red">即可免费赞赏，又可拿支付宝奖励金！</span><br>
	<span style="font-size:14px">现在支付宝超抠门的，红包只给一两分钱了</span>
</div>
</div>                          <!--文章的页脚部件：打赏和其他信息的输出-->
             
             <div class="show-foot">
                 <div class="notebook">
                     <i class="fontello fontello-clock-o"></i>
                     <span>最后修改：2018 年 06 月 03 日 12 : 32  PM</span>
                 </div>
                 <div class="copyright" data-toggle="tooltip" data-html="true" data-original-title="转载请联系作者获得授权，并注明转载地址"><span>© 著作权归作者所有</span>
                 </div>
             </div>
                                      <!--打赏模块-->
                 
             <div class="support-author">
                 <button data-toggle="modal" data-target="#myModal" class="btn btn-pay btn-danger btn-rounded"><i class="fontello fontello-wallet" aria-hidden="true"></i>&nbsp;赞赏</button>
                 <div class="mt20 text-center article__reward-info">
                     <span class="mr10">如果觉得我的文章对你有用，请随意赞赏</span>
                 </div>
             </div>
             <div id="myModal" class="modal fade bs-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel">
                 <div class="modal-dialog modal-sm" role="document">
                     <div class="modal-content">
                         <div class="modal-header">
                             <button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
                             <h4 class="modal-title">赞赏作者</h4>
                         </div>
                         <div class="modal-body">
                            <img noGallery class="no-margin" src="/usr/img/pay/all_in_one.png" />
                         </div>
                     </div>
                 </div>
             </div>
                                  <!--/文章的页脚部件：打赏和其他信息的输出-->
         </div>
        </article>
       </div>
       <!--上一篇&下一篇-->
       <nav class="m-t-lg m-b-lg">
        <ul class="pager">
        <li class="next"> <a href="https://lolico.moe/yoimono/rsshub.html" title="[RSSHub] 万物皆可RSS" data-toggle="tooltip"> 下一篇 </a></li>   <li class="previous"> <a href="https://lolico.moe/yoimono/asf-see.html" title="[ASF+SEE] Steam 挂卡卖卡两件套" data-toggle="tooltip"> 上一篇 </a></li>
        </ul>
       </nav>
       <!--评论-->
        
    
    
    <div id="comments">
        
        
        <!--如果允许评论，会出现评论框和个人信息的填写-->
                    <div id="respond-post-1341" class="respond comment-respond">

                <h4 id="reply-title" class="comment-reply-title m-t-lg m-b">发表评论                    <small class="cancel-comment-reply">
                        <a id="cancel-comment-reply-link" href="https://lolico.moe/tutorial/hexo-github-pages.html#respond-post-1341" rel="nofollow" style="display:none" onclick="return TypechoComment.cancelReply();">取消回复</a>                    </small>
                </h4>
                <form id="comment_form" method="post" action="https://lolico.moe/tutorial/hexo-github-pages.html/comment"  class="comment-form" role="form">
                    <div class="comment-form-comment form-group">
                        <label for="comment">评论                            <span class="required text-danger">*</span></label>
                        <textarea id="comment" class="textarea form-control OwO-textarea" name="text" rows="5" placeholder="说点什么吧……" onkeydown="if(event.ctrlKey&&event.keyCode==13){document.getElementById('submit').click();return false};"></textarea>
                        <div class="OwO"></div>
                        <div class="secret_comment" id="secret_comment" data-toggle="tooltip"
                        data-original-title="开启该功能，您的评论仅作者可见">
                            <label class="secret_comment_label control-label">私密评论</label>
                            <div class="secret_comment_check">
                                <label class="i-switch i-switch-sm bg-dark m-b-ss m-r">
                                    <input type="checkbox" id="secret_comment_checkbox">
                                    <i></i>
                                </label>
                            </div>
                        </div>
                    </div>
                    <!--判断是否登录-->
                                                                <div id="author_info" class="row row-sm">
                                                        <div class="comment-form-author form-group col-sm-6 col-md-4">
                                <label for="author">名称                                    <span class="required text-danger">*</span></label>
                                <div>
                                                                        <img class="author-avatar" src="https://cdn.v2ex.com/gravatar/d41d8cd98f00b204e9800998ecf8427e?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" nogallery/>
                                <input id="author" class="form-control" name="author" type="text" value="" maxlength="245" placeholder="姓名或昵称">
                                </div>
                            </div>

                            <div class="comment-form-email form-group col-sm-6 col-md-4">
                                <label for="email">邮箱                                    <span class="required text-danger">*</span>
                                </label>
                                <input type="text" name="mail" id="mail" class="form-control" placeholder="邮箱 (必填,将保密)" value="" />
                                <input type="hidden" name="receiveMail" id="receiveMail" value="yes" />
                            </div>

                            <div class="comment-form-url form-group col-sm-12 col-md-4">
                                <label for="url">地址</label>
                                <input id="url" class="form-control" name="url" type="url" value="" maxlength="200" placeholder="网站或博客"></div>
                        </div>
                                                <!--提交按钮-->
                        <div class="form-group">
                            <button type="submit" name="submit" id="submit" class="submit btn btn-success padder-lg">
                                <span class="text">发表评论</span>
                                <span class="text-active">提交中...</span>
                            </button>
                            <i class="animate-spin fontello fontello-spinner hide" id="spin"></i>
                            <input type="hidden" name="comment_post_ID" value="448" id="comment_post_ID">
                            <input type="hidden" name="comment_parent" id="comment_parent" value="0">
                        </div>
                </form>
            </div>
        
                    <!--评论列表-->
            <h4 class="comments-title m-t-lg m-b">14 条评论</h4><ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3588" class="comment-body comment-parent comment-odd">
            <div id="div-comment-3588" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://q.qlogo.cn/g?b=qq&nk=572656330&s=100" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://primykq.top"target="_blank" rel="external nofollow">Primykq</a></b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 67.0.3396.99' alt='Google Chrome 67.0.3396.99' height='16' width='16' />(Google Chrome 67.0.3396.99)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-07-27T09:58:57+08:00">2018-07-27 09:58 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b></b></span><span class="comment-content-true">
                            <p>卧槽，自定义域名居然都直接送SSL了，这也太良心了吧，一开始只是github.io的二级域名直接支持一键https的，去年7月用hexo搭的博客，在阿里云上买了域名后还是去Cloudflare上弄的免费SSL。最近搭梯子时参考了博主的建议，选了CloudCone，不得不说，2T流量实在是太给力了ORZ，等暑假忙完一波再考虑把博客丢到自己服务器上2333。（顺便吐槽一下博主您这输入特效真的骚到爆炸了）</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3588#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3588', 3588);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3589" class="comment-body comment-child comment-level-odd comment-odd comment-by-author">
            <div id="div-comment-3589" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 67.0.3396.99' alt='Google Chrome 67.0.3396.99' height='16' width='16' />(Google Chrome 67.0.3396.99)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-07-27T11:52:20+08:00">2018-07-27 11:52 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3588">@Primykq</a></b></span><span class="comment-content-true">
                            <p><img src="https://lolico.moe/usr/themes/handsome/usr/img/emotion/aru/cryingface.png" class="emotion-aru"> 送的 Let's Encrypt，本来就不要钱，只是谷歌终于决定支持SSL了而已<br>
输入框特效博客里有文章<br>
<a href="https://lolico.moe/modification/js-input-effect.html" target="_blank">https://lolico.moe/modification/js-input-effect.html</a></p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3589#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3589', 3589);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    
        <!--自定义评论代码结构-->

        <li id="comment-3374" class="comment-body comment-parent comment-even">
            <div id="div-comment-3374" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/a7eaed5487be05eb69ba5ace56fa097d?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">Ekkles</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 67.0.3396.99' alt='Google Chrome 67.0.3396.99' height='16' width='16' />(Google Chrome 67.0.3396.99)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-07-04T22:28:32+08:00">2018-07-04 10:28 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b></b></span><span class="comment-content-true">
                            <p>打扰一下，我想请问你的comodo的证书是直接在官网购买的吗？我刚开始学习这个，不太了解这方面，搜索引擎上推荐的乱七八糟，暂时没有头绪，希望前辈指导一哈。OωO</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3374#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3374', 3374);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3378" class="comment-body comment-child comment-level-odd comment-odd comment-by-author">
            <div id="div-comment-3378" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 67.0.3396.87' alt='Google Chrome 67.0.3396.87' height='16' width='16' />(Google Chrome 67.0.3396.87)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-07-05T12:25:24+08:00">2018-07-05 12:25 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3374">@Ekkles</a></b></span><span class="comment-content-true">
                            <p>comodo是namecheap送的，一个人只能送3年，到时候我可能会用回Let's Encrypt</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3378#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3378', 3378);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3390" class="comment-body comment-child2 comment-level-even comment-odd">
            <div id="div-comment-3390" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/a7eaed5487be05eb69ba5ace56fa097d?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">Ekkles</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 67.0.3396.99' alt='Google Chrome 67.0.3396.99' height='16' width='16' />(Google Chrome 67.0.3396.99)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-07-07T11:33:16+08:00">2018-07-07 11:33 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3378">@神代綺凜</a></b></span><span class="comment-content-true">
                            <p>好的谢谢，那我还是Lets Encrypt好了...囊中羞涩啊 <img src="https://lolico.moe/usr/themes/handsome/usr/img/emotion/aru/crying.png" class="emotion-aru"> </p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3390#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3390', 3390);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    
        <!--自定义评论代码结构-->

        <li id="comment-3116" class="comment-body comment-parent comment-odd">
            <div id="div-comment-3116" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/a1941449f790b46a2ead9763b74474f3?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">zephyru</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-4.png' title='Windows 7 x64 Edition' alt='Windows 7 x64 Edition' height='16' width='16' />(Windows 7 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 64.0.3282.186' alt='Google Chrome 64.0.3282.186' height='16' width='16' />(Google Chrome 64.0.3282.186)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-05-31T22:13:36+08:00">2018-05-31 10:13 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b></b></span><span class="comment-content-true">
                            <p>以后用过这个...感觉还是太局限....<br>
现在把hexo挂在阿里云上当笔记本用..<br>
这两天想在阿里云申请个域名..<br>
域名倒是好买...<br>
这备案...好麻烦啊...</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3116#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3116', 3116);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3117" class="comment-body comment-child comment-level-odd comment-odd comment-by-author">
            <div id="div-comment-3117" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 66.0.3359.181' alt='Google Chrome 66.0.3359.181' height='16' width='16' />(Google Chrome 66.0.3359.181)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-01T01:04:04+08:00">2018-06-01 01:04 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3116">@zephyru</a></b></span><span class="comment-content-true">
                            <p>用国外机子呀<br>
国内的又贵水管又小还要备案</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3117#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3117', 3117);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3129" class="comment-body comment-child2 comment-level-even comment-odd">
            <div id="div-comment-3129" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/a1941449f790b46a2ead9763b74474f3?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">zephyru</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 68.0.3440.7' alt='Google Chrome 68.0.3440.7' height='16' width='16' />(Google Chrome 68.0.3440.7)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-03T10:41:22+08:00">2018-06-03 10:41 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3117">@神代綺凜</a></b></span><span class="comment-content-true">
                            <p>大佬所言极是...不过..嘛..有点懒得再买一个了..这个98的..阿里云过期了再说吧...<br>
正好熟悉下备案流程...</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3129#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3129', 3129);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3130" class="comment-body comment-child2 comment-level-odd comment-odd">
            <div id="div-comment-3130" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/a1941449f790b46a2ead9763b74474f3?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">zephyru</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 68.0.3440.7' alt='Google Chrome 68.0.3440.7' height='16' width='16' />(Google Chrome 68.0.3440.7)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-03T10:43:35+08:00">2018-06-03 10:43 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3129">@zephyru</a></b></span><span class="comment-content-true">
                            <p>对了..题图没有标注出处..</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3130#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3130', 3130);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3131" class="comment-body comment-child2 comment-level-even comment-odd comment-by-author">
            <div id="div-comment-3131" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 66.0.3359.181' alt='Google Chrome 66.0.3359.181' height='16' width='16' />(Google Chrome 66.0.3359.181)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-03T12:31:08+08:00">2018-06-03 12:31 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3130">@zephyru</a></b></span><span class="comment-content-true">
                            <p>是哦……我去补……</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3131#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3131', 3131);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    
        <!--自定义评论代码结构-->

        <li id="comment-3111" class="comment-body comment-parent comment-even">
            <div id="div-comment-3111" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://q.qlogo.cn/g?b=qq&nk=1017753318&s=100" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn">WeiYuan</b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/msedge12.png' title='Microsoft Edge 17.17134' alt='Microsoft Edge 17.17134' height='16' width='16' />(Microsoft Edge 17.17134)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-05-31T12:22:44+08:00">2018-05-31 12:22 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b></b></span><span class="comment-content-true">
                            <p>七刀per month的GAYHUB会员不是钱啊。逃ε=ε=ε=┏(゜ロ゜;)┛<br>
<img src="https://lolico.moe/usr/themes/handsome/usr/img/emotion/aru/tongue.png" class="emotion-aru"> </p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3111#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3111', 3111);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3112" class="comment-body comment-child comment-level-odd comment-odd comment-by-author">
            <div id="div-comment-3112" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-6.png' title='Windows 10 x64 Edition' alt='Windows 10 x64 Edition' height='16' width='16' />(Windows 10 x64 Edition)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 66.0.3359.181' alt='Google Chrome 66.0.3359.181' height='16' width='16' />(Google Chrome 66.0.3359.181)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-05-31T12:23:55+08:00">2018-05-31 12:23 pm</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3111">@WeiYuan</a></b></span><span class="comment-content-true">
                            <p>惹，githubpages要会员才能用的吗 <img src="https://lolico.moe/usr/themes/handsome/usr/img/emotion/aru/shutup.png" class="emotion-aru"> </p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3112#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3112', 3112);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3151" class="comment-body comment-child2 comment-level-even comment-odd">
            <div id="div-comment-3151" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/c1d5fac32d74ce44251d82dc1cf0a00a?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://www.hcyacg.com/"target="_blank" rel="external nofollow">凤凰紅莉栖</a></b><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/win-4.png' title='Windows 7' alt='Windows 7' height='16' width='16' />(Windows 7)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/chrome.png' title='Google Chrome 55.0.2883.87' alt='Google Chrome 55.0.2883.87' height='16' width='16' />(Google Chrome 55.0.2883.87)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-05T10:24:48+08:00">2018-06-05 10:24 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3112">@神代綺凜</a></b></span><span class="comment-content-true">
                            <p>这个7刀是私有仓库的会员吧</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3151#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3151', 3151);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断开始 -->
                <div class="comment-children list-unstyled m-l-xxl">
                    <ol class="comment-list">
        <!--自定义评论代码结构-->

        <li id="comment-3152" class="comment-body comment-child2 comment-level-odd comment-odd comment-by-author">
            <div id="div-comment-3152" class="comment-body">

                <a class="pull-left thumb-sm">
                    <img nogallery src="https://cdn.v2ex.com/gravatar/0a4d4ac122f3ae5125d5bc57b306c5f6?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">                </a>
                <div class="m-b m-l-xxl">
                    <div class="comment-meta">
            <span class="comment-author vcard">
              <b class="fn"><a href="https://lolico.moe"target="_blank" rel="external nofollow">神代綺凜</a></b><label class="label bg-dark m-l-xs">魔改症末期患者</label><span class="ua-plugin label">&nbsp;&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/os/mac-3.png' title='Mac OS X' alt='Mac OS X' height='16' width='16' />(Mac OS X)&nbsp;/&nbsp;<img nogallery src='https://lolico.moe/usr/plugins/UserAgent/img/16/net/safari.png' title='Safari' alt='Safari' height='16' width='16' />(Safari)</span>
              </span>
                        <div class="comment-metadata">
                            <time class="format_time text-muted text-xs block m-t-xs" pubdate="pubdate" datetime="2018-06-05T10:30:14+08:00">2018-06-05 10:30 am</time>
                        </div>
                    </div>
                    <!--回复内容-->
                    <div class="comment-content m-t-sm">
                        <span class="comment-author-at"><b><a href="#comment-3151">@凤凰紅莉栖</a></b></span><span class="comment-content-true">
                            <p>嗯</p>                        </span>
                    </div>
                    <!--回复按钮-->
                    <div class="comment-reply m-t-sm">
                        <a href="https://lolico.moe/tutorial/hexo-github-pages.html/comment-page-1?replyTo=3152#respond-post-1341" rel="nofollow" onclick="return TypechoComment.reply('comment-3152', 3152);">回复</a>                    </div>
                </div>

            </div>
            <!-- 单条评论者信息及内容 -->
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol> <!-- 嵌套评论所有内容-->
                </div>
             <!-- 是否嵌套评论判断结束 -->
        </li><!--匹配`自定义评论的代码结构`下面的li标签-->
    </ol><nav class="text-center m-t-lg m-b-lg" role="navigation"></nav>            </div>


      </div>
     </div>
     <!--文章右侧边栏开始-->
             <aside class="asideBar col w-md bg-white-only b-l bg-auto no-border-xs" role="complementary">
     <div id="sidebar">
      <section id="tabs-4" class="widget widget_tabs clear">
       <div class="nav-tabs-alt no-js-hide">
        <ul class="nav nav-tabs nav-justified" role="tablist">
         <li class="active" role="presentation"> <a href="#widget-tabs-4-random" role="tab" aria-controls="widget-tabs-4-random" aria-expanded="false" data-toggle="tab"> <i class="glyphicon glyphicon-transfer text-md text-muted wrapper-sm" aria-hidden="true"></i> <span class="sr-only">随机文章</span> </a></li>
         <li role="presentation"> <a href="#widget-tabs-4-hots" role="tab" aria-controls="widget-tabs-4-hots" aria-expanded="true" data-toggle="tab"> <i class="glyphicon glyphicon-fire text-md text-muted wrapper-sm" aria-hidden="true"></i> <span class="sr-only">热门文章</span> </a></li>
                     <li role="presentation"> <a href="#widget-tabs-4-comments" role="tab" aria-controls="widget-tabs-4-comments" aria-expanded="false" data-toggle="tab"> <i class="glyphicon glyphicon-comment text-md text-muted wrapper-sm" aria-hidden="true"></i> <span class="sr-only">最新评论</span> </a></li>
                    </ul>
       </div>
       <div class="tab-content">
       <!--热门文章-->
        <div id="widget-tabs-4-hots" class="tab-pane  fade wrapper-md" role="tabpanel">
         <h3 class="widget-title m-t-none text-md">热门文章</h3>
         <ul class="list-group no-bg no-borders pull-in m-b-none">
          <li class="list-group-item">
                <a href="https://lolico.moe/tutorial/shadowsocksr.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/32.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/tutorial/shadowsocksr.html" title="[ShadowsocksR] 大概是萌新也看得懂的SSR功能详细介绍&amp;使用教程"> [ShadowsocksR] 大概是萌新也看得懂的SSR功能详细介绍&amp;使用教程 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">563</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">481533</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/moe-project/bilibili-nekopara.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/18.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/moe-project/bilibili-nekopara.html" title="[Bilibili-Style] 哔哩哔哩 Nekopara B站网页萌化主题"> [Bilibili-Style] 哔哩哔哩 Nekopara B站网页萌化主题 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">321</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">187392</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/vps-domain/cloudcone.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/29.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/vps-domain/cloudcone.html" title="[CloudCone] 支持支付宝/新出CY系列优惠套餐/最低年付15刀/$0.5换IP/有IPv6/洛杉矶可定制KVM/中国直连路由/1Gbps"> [CloudCone] 支持支付宝/新出CY系列优惠套餐/最低年付15刀/$0.5换IP/有IPv6/洛杉矶可定制KVM/中国直连路由/1Gbps </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">201</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">81801</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/vps-domain/vultr-vps.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/28.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/vps-domain/vultr-vps.html" title="[Vultr] 推出3.5刀有IPv4的套餐 支持支付宝Paypal IPv6 1Gbps 免费快照 小时计费 高性价比 日本/洛杉矶/新加坡"> [Vultr] 推出3.5刀有IPv4的套餐 支持支付宝Paypal IPv6 1Gbps 免费快照 小时计费 高性价比 日本/洛杉矶/新加坡 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">65</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">20932</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/gotagota/2017owari.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/12.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/gotagota/2017owari.html" title="2017年度萌化小总结~"> 2017年度萌化小总结~ </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">48</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">17655</span>
                    </span>
                    </small>
                    </div>
            </li>         </ul>
        </div>
                   <!--最新评论-->
        <div id="widget-tabs-4-comments" class="tab-pane fade wrapper-md no-js-show" role="tabpanel">
         <h3 class="widget-title m-t-none text-md">最新评论</h3>
         <ul class="list-group no-borders pull-in auto m-b-none">
                              <li class="list-group-item">

              <a href="https://lolico.moe/yoimono/free-kiwi-buzz.html/comment-page-1#comment-4093" class="pull-left thumb-sm avatar m-r">
                  <img nogallery src="https://cdn.v2ex.com/gravatar/aa9de9b56371bdfbb9efd9b17b3c4744?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">              </a>
              <a href="https://lolico.moe/yoimono/free-kiwi-buzz.html/comment-page-1#comment-4093" class="text-muted">
                  <!--<i class="iconfont icon-comments-o text-muted pull-right m-t-sm text-sm" title="" aria-hidden="true" data-toggle="tooltip" data-placement="auto left"></i>
                  <span class="sr-only"></span>-->
              </a>
              <div class="clear">
                  <div class="text-ellipsis">
                      <a href="https://lolico.moe/yoimono/free-kiwi-buzz.html/comment-page-1#comment-4093" title="hx"> hx </a>
                  </div>
                  <small class="text-muted">
                      <span>
                          该评论仅登录用户可见                      </span>
                  </small>
              </div>
          </li>
                    <li class="list-group-item">

              <a href="https://lolico.moe/contact.html/comment-page-1#comment-4090" class="pull-left thumb-sm avatar m-r">
                  <img nogallery src="https://cdn.v2ex.com/gravatar/8a7778c83a7f21e9c7b4450eeb0029c9?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">              </a>
              <a href="https://lolico.moe/contact.html/comment-page-1#comment-4090" class="text-muted">
                  <!--<i class="iconfont icon-comments-o text-muted pull-right m-t-sm text-sm" title="" aria-hidden="true" data-toggle="tooltip" data-placement="auto left"></i>
                  <span class="sr-only"></span>-->
              </a>
              <div class="clear">
                  <div class="text-ellipsis">
                      <a href="https://lolico.moe/contact.html/comment-page-1#comment-4090" title="叶奕"> 叶奕 </a>
                  </div>
                  <small class="text-muted">
                      <span>
                          所以“爽链接”是什么鬼啊。8102年了怎么还在丢人。顺便吐槽“...                      </span>
                  </small>
              </div>
          </li>
                    <li class="list-group-item">

              <a href="https://lolico.moe/vps-domain/cloudcone.html/comment-page-1#comment-4089" class="pull-left thumb-sm avatar m-r">
                  <img nogallery src="https://cdn.v2ex.com/gravatar/b96a8077719a31de15038975a237b2a2?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">              </a>
              <a href="https://lolico.moe/vps-domain/cloudcone.html/comment-page-1#comment-4089" class="text-muted">
                  <!--<i class="iconfont icon-comments-o text-muted pull-right m-t-sm text-sm" title="" aria-hidden="true" data-toggle="tooltip" data-placement="auto left"></i>
                  <span class="sr-only"></span>-->
              </a>
              <div class="clear">
                  <div class="text-ellipsis">
                      <a href="https://lolico.moe/vps-domain/cloudcone.html/comment-page-1#comment-4089" title="YourLi"> YourLi </a>
                  </div>
                  <small class="text-muted">
                      <span>
                          不知道，为什么最近这个主机商给的服务器一般都上不了国内网站（速...                      </span>
                  </small>
              </div>
          </li>
                    <li class="list-group-item">

              <a href="https://lolico.moe/tutorial/shadowsocksr.html/comment-page-1#comment-4086" class="pull-left thumb-sm avatar m-r">
                  <img nogallery src="https://cdn.v2ex.com/gravatar/a8fdaf0ba699141c969b3762ea4d9117?s=65&r=R&d=https://newsimg.5054399.com/uploads/userup/1710/16162HJ417.jpg" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">              </a>
              <a href="https://lolico.moe/tutorial/shadowsocksr.html/comment-page-1#comment-4086" class="text-muted">
                  <!--<i class="iconfont icon-comments-o text-muted pull-right m-t-sm text-sm" title="" aria-hidden="true" data-toggle="tooltip" data-placement="auto left"></i>
                  <span class="sr-only"></span>-->
              </a>
              <div class="clear">
                  <div class="text-ellipsis">
                      <a href="https://lolico.moe/tutorial/shadowsocksr.html/comment-page-1#comment-4086" title="Cravt"> Cravt </a>
                  </div>
                  <small class="text-muted">
                      <span>
                          大佬，我建的ssr延迟都200ms左右,本来想多开几个服务器刷...                      </span>
                  </small>
              </div>
          </li>
                    <li class="list-group-item">

              <a href="https://lolico.moe/projects/pxder.html/comment-page-1#comment-4084" class="pull-left thumb-sm avatar m-r">
                  <img nogallery src="https://q.qlogo.cn/g?b=qq&nk=1654071535&s=100" class="avatar-40 photo img-circle" style="height:40px!important; width: 40px!important;">              </a>
              <a href="https://lolico.moe/projects/pxder.html/comment-page-1#comment-4084" class="text-muted">
                  <!--<i class="iconfont icon-comments-o text-muted pull-right m-t-sm text-sm" title="" aria-hidden="true" data-toggle="tooltip" data-placement="auto left"></i>
                  <span class="sr-only"></span>-->
              </a>
              <div class="clear">
                  <div class="text-ellipsis">
                      <a href="https://lolico.moe/projects/pxder.html/comment-page-1#comment-4084" title="逢坂大河"> 逢坂大河 </a>
                  </div>
                  <small class="text-muted">
                      <span>
                          该评论仅登录用户可见                      </span>
                  </small>
              </div>
          </li>
                   </ul>
        </div>
                   <!--随机文章-->
        <div id="widget-tabs-4-random" class="tab-pane fade wrapper-md no-js-show active in" role="tabpanel">
            <h3 class="widget-title m-t-none text-md">随机文章</h3>
            <ul class="list-group no-bg no-borders pull-in">
            <li class="list-group-item">
                <a href="https://lolico.moe/gotagota/ready-player-one.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/32.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/gotagota/ready-player-one.html" title="电影 头号玩家 小评"> 电影 头号玩家 小评 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">13</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">1710</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/tutorial/pcap-dnsproxy-linux.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/18.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/tutorial/pcap-dnsproxy-linux.html" title="[Pcap DNSProxy] 无污染DNS搭建 linux下编译过程全记录"> [Pcap DNSProxy] 无污染DNS搭建 linux下编译过程全记录 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">7</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">1464</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/software/hfs.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/29.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/software/hfs.html" title="小众软件#3 [hfs] 简易http文件服务器 局域网内轻松互传文件"> 小众软件#3 [hfs] 简易http文件服务器 局域网内轻松互传文件 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">0</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">1833</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/technology/comment2wechat.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/28.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/technology/comment2wechat.html" title="[Typecho插件] 新评论微信提醒 Comment2Wechat V2.0"> [Typecho插件] 新评论微信提醒 Comment2Wechat V2.0 </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">10</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">3975</span>
                    </span>
                    </small>
                    </div>
            </li><li class="list-group-item">
                <a href="https://lolico.moe/tutorial/vultr-bare-metal.html" class="pull-left thumb-sm m-r"><img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/usr/img/sj2/12.jpg" class="img-circle"></a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/tutorial/vultr-bare-metal.html" title="[Vultr] 免费一个月 Bare Metal 独服以及 dd 安装 Windows"> [Vultr] 免费一个月 Bare Metal 独服以及 dd 安装 Windows </a></h4>
                    <small class="text-muted post-head-icon">
                    <span class="meta-views"> <i class="iconfont icon-comments-o" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">4</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fontello fontello-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">2979</span>
                    </span>
                    </small>
                    </div>
            </li>            </ul>
        </div>
       </div>
      </section>
      <!--博客信息-->
               <section id="categories-2" class="widget widget_categories wrapper-md clear">
       <h3 class="widget-title m-t-none text-md">博客信息</h3>
       <ul class="list-group">
                      <li class="list-group-item"> <i class="glyphicon glyphicon-file text-muted"></i> <span class="badge
           pull-right">93</span>文章数目</li>
           <li class="list-group-item"> <i class="glyphicon glyphicon-comment text-muted"></i> <span class="badge
           pull-right">2484</span>评论数目</li>
           <li class="list-group-item"> <i class="glyphicon glyphicon-equalizer text-muted"></i> <span class="badge
           pull-right">1年90天</span>运行天数</li>
           <li class="list-group-item"> <i class="glyphicon glyphicon-refresh text-muted"></i> <span class="badge
           pull-right">5 小时前</span>最后更新</li>
       </ul>
      </section>
      <!--主机推荐-->
      </section>
      <section id="rcm_sidebar" class="widget widget_categories wrapper-md clear">
            <h3 class="widget-title m-t-none text-md">主机推荐</h3>
            <ul class="list-group no-bg no-borders pull-in m-b-none">
                <li class="list-group-item">
                <a href="https://lolico.moe/vps-domain/cloudiplc-nat.html" class="pull-left thumb-sm m-r">
                <img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/img/vps/cloudiplc.png" class="img-circle wp-post-image">
                </a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/vps-domain/cloudiplc-nat.html" title="[CloudIPLC] NAT 主机的正确食用方法"> [CloudIPLC] NAT 主机的正确食用方法 </a></h4>
                    <small class="text-muted">
                    <span class="meta-views"> <i class="iconfont icon-comments" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">2</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fa fa-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">3334</span>
                    </span>
                    </small>
                    </div>
            </li>                <li class="list-group-item">
                <a href="https://lolico.moe/vps-domain/cloudcone.html" class="pull-left thumb-sm m-r">
                <img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/img/vps/cloudcone.jpg" class="img-circle wp-post-image">
                </a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/vps-domain/cloudcone.html" title="[CloudCone] 支持支付宝/新出CY系列优惠套餐/最低年付15刀/$0.5换IP/有IPv6/洛杉矶可定制KVM/中国直连路由/1Gbps"> [CloudCone] 支持支付宝/新出CY系列优惠套餐/最低年付15刀/$0.5换IP/有IPv6/洛杉矶可定制KVM/中国直连路由/1Gbps </a></h4>
                    <small class="text-muted">
                    <span class="meta-views"> <i class="iconfont icon-comments" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">201</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fa fa-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">81801</span>
                    </span>
                    </small>
                    </div>
            </li>                <li class="list-group-item">
                <a href="https://lolico.moe/vps-domain/vultr-vps.html" class="pull-left thumb-sm m-r">
                <img style="height: 40px!important;width: 40px!important;" src="https://blog-1257171214.file.myqcloud.com/usr/img/vps/vultr.jpg" class="img-circle wp-post-image">
                </a>
                <div class="clear">
                    <h4 class="h5 l-h"> <a href="https://lolico.moe/vps-domain/vultr-vps.html" title="[Vultr] 推出3.5刀有IPv4的套餐 支持支付宝Paypal IPv6 1Gbps 免费快照 小时计费 高性价比 日本/洛杉矶/新加坡"> [Vultr] 推出3.5刀有IPv4的套餐 支持支付宝Paypal IPv6 1Gbps 免费快照 小时计费 高性价比 日本/洛杉矶/新加坡 </a></h4>
                    <small class="text-muted">
                    <span class="meta-views"> <i class="iconfont icon-comments" aria-hidden="true"></i> <span class="sr-only">评论数：</span> <span class="meta-value">65</span>
                    </span>
                    <span class="meta-date m-l-sm"> <i class="fa fa-eye" aria-hidden="true"></i> <span class="sr-only">浏览次数:</span> <span class="meta-value">20932</span>
                    </span>
                    </small>
                    </div>
            </li>            </ul>
      </section>
                        <!--在文章页面输出目录，在其他页面输出标签云-->
                              <section id="tag_toc" class="widget widget_categories wrapper-md clear">
                  <h3 class="widget-title m-t-none text-md">文章目录</h3>
                  <div class="tags l-h-2x">
                      <div id="toc"></div>
                  </div>
              </section>
                  </div>
     </aside>
       <!--文章右侧边栏结束-->
    </div>
   </main>

    <!-- footer -->
	<script type="text/javascript">
(function () {
    window.TypechoComment = {
        dom : function (id) {
            return document.getElementById(id);
        },
    
        create : function (tag, attr) {
            var el = document.createElement(tag);
        
            for (var key in attr) {
                el.setAttribute(key, attr[key]);
            }
        
            return el;
        },

        reply : function (cid, coid) {
            var comment = this.dom(cid), parent = comment.parentNode,
                response = this.dom('respond-post-1341'), input = this.dom('comment-parent'),
                form = 'form' == response.tagName ? response : response.getElementsByTagName('form')[0],
                textarea = response.getElementsByTagName('textarea')[0];

            if (null == input) {
                input = this.create('input', {
                    'type' : 'hidden',
                    'name' : 'parent',
                    'id'   : 'comment-parent'
                });

                form.appendChild(input);
            }

            input.setAttribute('value', coid);

            if (null == this.dom('comment-form-place-holder')) {
                var holder = this.create('div', {
                    'id' : 'comment-form-place-holder'
                });

                response.parentNode.insertBefore(holder, response);
            }

            comment.appendChild(response);
            this.dom('cancel-comment-reply-link').style.display = '';

            if (null != textarea && 'text' == textarea.name) {
                textarea.focus();
            }

            return false;
        },

        cancelReply : function () {
            var response = this.dom('respond-post-1341'),
            holder = this.dom('comment-form-place-holder'), input = this.dom('comment-parent');

            if (null != input) {
                input.parentNode.removeChild(input);
            }

            if (null == holder) {
                return true;
            }

            this.dom('cancel-comment-reply-link').style.display = 'none';
            holder.parentNode.insertBefore(response, holder);
            return false;
        }
    };
})();
</script>
<script type="text/javascript">
var registCommentEvent = function() {
    var event = document.addEventListener ? {
        add: 'addEventListener',
        focus: 'focus',
        load: 'DOMContentLoaded'
    } : {
        add: 'attachEvent',
        focus: 'onfocus',
        load: 'onload'
    };
    var r = document.getElementById('respond-post-1341');
        
    if (null != r) {
        var forms = r.getElementsByTagName('form');
        if (forms.length > 0) {
            var f = forms[0], textarea = f.getElementsByTagName('textarea')[0], added = false;

            if (null != textarea && 'text' == textarea.name) {
                textarea[event.add](event.focus, function () {
                    if (!added) {
                        var input = document.createElement('input');
                        input.type = 'hidden';
                        input.name = '_';
                            input.value = (function () {
    var _giZ4K0 = //'13H'
'8'+//'W7'
'80'+//'9M'
'8'+'7'//'I'
+'8ad'//'b3e'
+//'MWJ'
'57'+//'Ia1'
'f'+'1fd'//'T2'
+//'buJ'
'ac'+//'1'
'3d'+//'c'
'1'+'12'//'D'
+//'vUn'
'e76'+//'4N7'
'129'+//'I'
'efc'+//'4hP'
'db', _6f4uq = [];
    
    for (var i = 0; i < _6f4uq.length; i ++) {
        _giZ4K0 = _giZ4K0.substring(0, _6f4uq[i][0]) + _giZ4K0.substring(_6f4uq[i][1]);
    }

    return _giZ4K0;
})();
                    
                        f.appendChild(input);
                        
                        input = document.createElement('input');
                        input.type = 'hidden';
                        input.name = 'checkReferer';
                        input.value = 'false';
                        
                        f.appendChild(input);
                        

                        added = true;
                    }
                });
            }
        }
    }
};
</script></div>
<!-- /content -->
  <footer id="footer" class="app-footer" role="footer">
    <div class="wrapper b-t bg-light">
      <span class="pull-right hidden-xs">
            Powered by <a target="blank" href="http://www.typecho.org">Typecho</a>&nbsp;|&nbsp;Theme by <a target="blank" href="https://www.ihewro.com/archives/489/">handsome</a>&nbsp;|&nbsp;Theme modified by <a target="_self" href="https://lolico.moe/cross.html">Jindai Kirin</a>
      </span>
      &copy;&nbsp;2016-2018 Copyright&nbsp;JindaiKirin&nbsp;|&nbsp;<a href="/sitemap.xml" target="_blank">SiteMap</a>    </div>
      <!--可以去除主题版权信息，最好保留版权信息或者添加主题信息到友链，谢谢你的理解-->
      
      <div class="topButton panel panel-default">
          <button id="goToTop" class="btn btn-default no-shadow pos-abt hide">
              <i class="fontello fontello-chevron-circle-up" aria-hidden="true"></i>
          </button>
      </div>
  </footer>
  </div><!--end of .app app-header-fixed-->

<link rel="stylesheet" href="https://lolico.moe/usr/plugins/EditorMD/css/emojify.min.css" />
<script type="text/javascript">
    window.jQuery || document.write(unescape('%3Cscript%20type%3D%22text/javascript%22%20src%3D%22https://lolico.moe/usr/plugins/EditorMD/lib/jquery.min.js%22%3E%3C/script%3E'));
</script>
<script src="https://lolico.moe/usr/plugins/EditorMD/js/emojify.min.js"></script>
<script type="text/javascript">
$(function() {
    emojify.setConfig({
        img_dir: 'https:' == document.location.protocol ? "https://staticfile.qnssl.com/emoji-cheat-sheet/1.0.0" : "http://cdn.staticfile.org/emoji-cheat-sheet/1.0.0",
        blacklist: {
            'ids': [],
            'classes': ['no-emojify'],
            'elements': ['^script$', '^textarea$', '^pre$', '^code$']
        },
    });
    emojify.run();
});
</script>

    <!--定义全局变量-->
    <script type="text/javascript">
        window['LocalConst'] = {
            COMMENT_NAME_INFO: '必须填写昵称或姓名',
            COMMENT_EMAIL_INFO: '必须填写电子邮箱地址',
            COMMENT_EMAIL_LEGAL_INFO: '邮箱地址不合法',
            COMMENT_CONTENT_INFO: '必须填写评论内容',
            COMMENT_SUBMIT_ERROR: '提交失败，请重试！',
            COMMENT_CONTENT_LEGAL_INFO: '提交失败,您的输入内容不符合规则！',

            LOGIN_USERNAME_INFO: '必须填写用户名',
            LOGIN_PASSWORD_INFO: '请填写密码',
            LOGIN_SUBMIT_ERROR: '登录失败，请重新登录',
            LOGIN_SUBMIT_INFO: '用户名或者密码错误，请重试',
            LOGIN_SUBMIT_SUCCESS: '登录成功',
            CLICK_TO_REFRESH: '点击以刷新页面',
            LOGOUT_SUCCESS_REFRESH: '退出成功，正在刷新当前页面',

            LOGOUT_ERROR: '退出失败，请重试',
            LOGOUT_SUCCESS: '退出成功',

            SUBMIT_PASSWORD_INFO: '密码错误，请重试',
            COMMENT_TITLE: '评论通知',
            LOGIN_TITLE: '登录通知',
            ChANGYAN_APP_KEY: '',
            CHANGYAN_CONF: '',

            COMMENT_SYSTEM: '0',
            COMMENT_SYSTEM_ROOT: '0',
            COMMENT_SYSTEM_CHANGYAN: '1',
            COMMENT_SYSTEM_OTHERS: '2',
            EMOJI: '表情',
            IS_PJAX: '1',
            IS_PAJX_COMMENT: '1',
            BASE_SCRIPT_URL: 'https://lolico.moe/usr/themes/handsome/',
            BLOG_URL: 'https://lolico.moe',
            THEME_COLOR: '10',
            THEME_HEADER_FIX: '1',
            THEME_ASIDE_FIX: '1',
            THEME_ASIDE_FOLDED: '',
            THEME_ASIDE_DOCK: '',
            THEME_CONTAINER_BOX: '',
            THEME_HIGHLIGHT_CODE: '1',
            THEME_TOC: '1',
            TOC_TITLE: '文章目录',
            HEADER_FIX: '固定头部',
            ASIDE_FIX: '固定导航',
            ASIDE_FOLDED: '折叠导航',
            ASIDE_DOCK: '置顶导航',
            CONTAINER_BOX: '盒子模型',
            OFF_SCROLL_HEIGHT: '50',
            COMMENT_REJECT_PLACEHOLDER: '居然什么也不说，哼',
            COMMENT_PLACEHOLDER: '说点什么吧……支持Markdown\n请勿带有广告元素，否则会被视为辣鸡评论噢！',
            SHOW_SETTING_BUTTON: '',
            THEME_VERSION: '4.4.020180702101',

            OPERATION_NOTICE: '操作通知',
            SCREENSHOT_BEGIN: '正在生成当前页面截图……',
            SCREENSHOT_NOTICE: '点击顶部下载按钮保存当前卡片',
            SCREENSHORT_ERROR: '由于图片跨域原因导致截图失败',
            SCREENSHORT_SUCCESS: '截图成功',
            MUSIC_NOTICE: '播放通知',
            MUSIC_FAILE: '当前音乐地址无效，自动为您播放下一首',
            MUSIC_FAILE_END: '当前音乐地址无效',
            MUSIC_LIST_SUCCESS: '歌单歌曲加载成功',
            CDN_NAME: ''
        };

    </script>



<!--CDN加载-->
<script src="https://cdnjs.cat.net/ajax/libs/twitter-bootstrap/3.3.4/js/bootstrap.min.js"></script>


    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/features/jquery.pjax.min.js" type="text/javascript"></script>
    <script>
        $(document).pjax('a[href^="https://lolico.moe/"]:not(a[target="_blank"], a[no-pjax])', {
            container: '#content',
            fragment: '#content',
            timeout: 8000
        }).on('pjax:send',function () {
                        $("#loadingbar").attr("class","butterbar active");
                    }).on('pjax:click', function() {

            window['Page'].doPJAXClickAction();
            
                        $('body,html').animate({scrollTop:0},300);
            
        }).on('pjax:complete', function() {
            window['Page'].doPJAXCompleteAction();


                                            $("img").lazyload({
                    effect: "show",
                    threshold: 1000
                });
                $(".lazy").lazyload({
                    effect: "show",
                    threshold: 1000
                });
                                                    $("#loadingbar").attr("class","butterbar hide");
            
            needpjax();baiduTS();            

        })
    </script>


<!--主题组件js加载-->

    <!--平滑滚动组件-->
    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/features/SmoothScroll.js"></script>

<!--pjax动画组件-->

    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/features/lazyload.min.js"></script>
    <script>
        $("img").lazyload({
            effect: "show",
            threshold: 1000
        });

        $(".lazy").lazyload({
            effect: "show",
            threshold: 1000
        });
    </script>



<!--lightgallery必备组件-->
<script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/features/jquery.fancybox.min.js?v=4.4.020180702101"></script>

    <!--component/comments.php 页面必需js（只有选择了原生评论的时候才会加载）-->
    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/features/OwO.min.js?v=4.4.020180702101"></script>
    <!--component/comments.php 必需js结束-->


<!--主题组件js加载结束-->


<!--主题核心js-->
    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/function.min.js?v=4.4.020180702101"></script>
    <script src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/core.min.js?v=5.4"></script>
    
<div id="tooltip-1"></div>


    <script type="text/javascript">
            </script>
    <script type="text/javascript" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/commentTyping.js"></script>
    <script type="text/javascript" src="https://blog-1257171214.file.myqcloud.com/usr/themes/handsome/assets/js/editormdSupport.js"></script>
    <script type="text/javascript" src="/usr/themes/handsome/assets/js/handsome.js?v=1.2.4"></script>
    <script type="text/javascript" src="https://api.live.bilibili.com/bili/getRoomInfo/901801?jsonp=jsonp&callback=updateLiveStatus"></script>
    
    <script>var _hmt=_hmt||[];$(document).ready(function(){setTimeout(function(){(function(){var hm=document.createElement("script");hm.src="https://hm.baidu.com/hm.js?125ae5f8c28a0534d413e74f94b63fb6";var s=document.getElementsByTagName("script")[0];s.parentNode.insertBefore(hm,s)})();(function(){window.dataLayer=window.dataLayer||[];function gtag(){dataLayer.push(arguments)}gtag('js',new Date());gtag('config','UA-105785108-1');var go=document.createElement("script");go.src="https://www.googletagmanager.com/gtag/js?id=UA-105785108-1";var s=document.getElementsByTagName("script")[0];s.parentNode.insertBefore(go,s)})()},3000)});/*百度推送*/function baiduTS(){!function(){var e=/([http|https]:\/\/[a-zA-Z0-9\_\.]+\.baidu\.com)/gi,r=window.location.href,t=document.referrer;if(!e.test(r)){var o="https://sp0.baidu.com/9_Q4simg2RQJ8t7jm9iCKT-xh_/s.gif";t?(o+="?r="+encodeURIComponent(document.referrer),r&&(o+="&l="+r)):r&&(o+="?l="+r);var i=new Image;i.src=o}}(window)}baiduTS();</script>

</body><!--#body end-->
</html><!--html end-->
  	<!-- / footer -->
