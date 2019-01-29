# XVersionUpdate
## 快速实现版本更新功能
![image](http://img.blog.csdn.net/20170523162052660?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYTE1MzM1ODg4Njc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)   
## 1.添加依赖 
       compile 'com.androidkun:xversionupdate:1.0.11' // 修复多次更新，App闪退的问题
   
    //compile 'com.androidkun:xversionupdate:1.0.5' // 此版本通知栏颜色为白色，跟目前大部分手机的通知栏白色底色冲突
    //compile 'com.github.neccy:XVersionUpdate:v1.0.0' // 此版本通知栏标题为黑色，在目前大部分手机的通知栏可明显看清楚通知的标题和内容

## 2.调用APII实现版本更新
   
      VersionUpdateConfig.getInstance()//获取配置实例
           .setContext(MainActivity.this)//设置上下文
           .setDownLoadURL(url)//设置文件下载链接 
           .setNewVersion("1.0.1")//设置即将下载的APK的版本号,避免重复下载
           .setFileSavePath(savePath)//设置文件保存路径（可不设置）
           .setNotificationIconRes(R.mipmap.app_icon)//设置通知图标
           .setNotificationSmallIconRes(R.mipmap.app_icon_small)//设置通知小图标
           .setNotificationTitle("版本升级Demo")//设置通知标题
           .startDownLoad();//开始下载
  
 ## 接下来就不用再做任何处理了，会自动弹出通知显示下载进度并下载完成后会自动跳到安装页面。
