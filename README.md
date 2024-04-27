一个封装了一些Qt函数的库

更新
20240427
1.在Windows上，添加对cppWinRT库的支持，添加相关头文件，链接了windowsapp库，并手动修复了winrt::impl错误

2.在Android上，完善了文件Uri转换机制，更改了Android::getRealPathFromUri()，新增了Android::getExternalStorageUriFromPath()和Android::getRealPathFromExternalStorageUri()
3.增加了Android::disableStrictMode()，用于在Android 7以上关闭严格模式，以使用file://开头的uri在应用间共享文件
4.重写了Android::showNotification()，增加了Android::closeNotification()，在Android上发送通知不再依赖于独立的java代码，完全在c++层进行操作，添加繁忙进度条通知
5.更改了Android::requestStroagePermission()，适配Android13以上的新文件权限机制
6.新增getApplicationIcon()，跨平台获取程序图标
7.新增Android::setNativeWallpaper()和Windows::setNativeWallpaper()以添加壁纸支持，后续将整合为跨平台接口
8.新增calculateHash(),calculateHashFromByte(),getMd5(),getMd5FromByte(),getSha1(),getSha1FromByte()，用于获取文件哈希值
9.除此之外，添加的方法有：
Android::getTargetSdkVersion()
Android::getActivityName()
Android::getApplicationDefaultIconId()
Android::getApplicationIconId()
Windows::hideFile()
Windows::getWallpaperPath()
更改的方法有：
Android::shareFile()
Android::startIntent()
Android::hasStroagePermission()
