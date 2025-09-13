AKWasTakenoooo's FCM Hosts for CN
====================

Overview:
---------
- 因为原作者更新此模块频率低，IP地址几乎失效，故fork此项目已进行维护
- A Magisk module integrated with FCM hosts for Chinese users
- Support Magisk / KernelSU / APatch root implementations.

Credits:
--------

- [@topjohnwu](https://github.com/topjohnwu) / Magisk - Magisk Module Template.
- [@entr0pia](https://github.com/entr0pia) / Base hosts sources.
- [@JumbomanXDA](https://github.com/JumbomanXDA) / Custom installation script.

QAs:
----

- fcm推送常见问题(特别是针对微信)：
首先确保使用的不是jingmatrix的lsposed，可以换成： [@lsp_leaks](t.me/lsp_leaks)或 [@lsposed_irena](t.me/lsposed_irena)

- 打开fcm diagnostics：
打开Android 设备的FCM Diagnostics 页面，请在拨号盘中输入代码 *#*#426#*#*，然后点击呼叫按钮。也可以使用 adb 命令 adb shell am start -n com.google.android.gms/.gcm.GcmDiagnostics 来打开该诊断页面。﻿

- 确定问题及解决方案：
0.CN版本ROM：例如ColorOS/RealmeUI，MIUI/HyperOS_CN，OneUI_CN等等，请自行替换电池软件为国际版（大部分系统默认在连不上Google的情况下就算有完整的GMS也会掐断FCM push），微信电池设置为优化，并移除微信电池白名单（方法自行寻找，我用类AOSP，不存在这个问题）
最好的办法就是刷成国际版ROM，还没广告😀

- 1.没连接上fcm：刷我的模块，然后将mtalk.google.com加入直连名单
或者开允许应用绕过，fcm自动绕过vpn

- 2.Failed to broadcast to stopped app com.tencent.mm (priority=HIGH)：装[fcmfix](https://modules.lsposed.org/module/com.kooritea.fcmfix/)
并勾选相关应用

- 针对微信：
请使用Google play版本wechat，打开微信设置内退出登录，然后把微信强行停止下，接着开vpn全局再打开微信重新登录后测试消息应该会有日志

- 鉴定微信是否由fcm推送：
消息带有头像是微信自己推送的，没有头像是fcm push，有时候fcm push也会存在有头像的情况：第一条通知来了fcm叫醒微信，微信醒了推送了通知但还没有被kill或者进缓存时候有第二条消息，第二条消息就会走微信的推送

- 番外篇：
其实99%CN ROM用户自己安装的GMS是阉割版，功能有缺失，例如不能使用查找手机，Google quick share，当然FCM也是阉割了的😁
可能的解决方法（我没试过因为我从来不用CN ROM，但我朋友试了一下好像有用）：刷入[Unlock CN GMS模块](https://github.com/fei-ke/unlock-cn-gms)

祝你早日用上满血fcm push，ins美女开播第一时间收到通知😃

推广可爱韩国🇰🇷coser：
https://www.instagram.com/yasal_170/
https://x.com/Yasal_170
https://space.bilibili.com/3546937055775240
