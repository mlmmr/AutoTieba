说明：
===
更新历史
---
### 2015-03-12<br />
        发布贴吧后台签到脚本1.0版。
        支持自动登录，自动获取关注贴吧，每日自动签到。
        支持登陆失败手工输入验证码。
        支持出错发送邮件提醒。
        支持日志记录。
部署说明
---
        脚本启动命令php index.php Script\\TiebaScript
        index.php中的调试模式可以设置是否打印日志到控制台，后台运行时建议关闭，手动验证码模式下建议开启。
        config.php设置脚本运行随机循环时间的最大值和最小值以及签到账号列表。
        Action/BaiduAction.ini设置是否手动输入验证码模式，见下方详细说明。建议第一次运行脚本时开启，确保Cookie能正确获得。再次运行时关闭。
手动输入验证码
---
        由于VPS的IP和家用电脑IP通常不在一个区域，所以登陆时可能会需要输入验证码，此时若不开启手动模式则会报错并发送邮件提醒。
        通常建议首次部署脚本时开启此项。
        如果此时开启手动输入验证码模式，则将验证码图片下载至Runtime/Verify/img.jpg。
        此时应该手动查看此图片并将验证码输入Runtime/Verify/verifycode.ini中并设置status值为1代表已输入完成。
        带验证码登陆成功后，应该及时手动设置status为0防止脚本死循环。
        建议此时应停止脚本，关闭手动验证码模式，重新运行脚本，此时便可以持续运行，每日自动签到了。
软件简介：
---
        软件基于自己编写的简易脚本框架MiniScript制作。
        实现了贴吧的自动登录和签到功能，无需手动输入cookie。
        自动扫描所有关注贴吧并执行签到操作，反馈结果。
        登陆部分参考了www.qaulau.com/php-simulated-login-baidu的代码。
        签到部分参考了部分网络代码。
注意：
---
        本软件致力于用于VPS或本机的长期运行的后台脚本。一次运行，长期无忧。
        由于未做过多的安全及加密处理，所以不建议将本软件部署于公网的web服务器环境中。
        