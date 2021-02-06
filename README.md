HP-400G3-DM-EFI 惠普400G3安装黑苹果使用的EFI引导文件，OC0.6.6

CPU：QL3X（魔改CPU）

实测:59120000，591B0000，19160000等缓冲帧都可以支持单显示器正常输出（如果出现紫屏可以用显示器EDID注入或者一键HiDPi脚本解决），所有尝试的缓冲帧都在NVRAM参数里面

结果多次优化，目前感觉最优选择是：

启动参数加入 -disablegfxfirmware（由于主板ME问题导致睡眠异常，不加此参数会卡核显） igfxonln=1 （多个显示器强制上线，单显示器请无视） 缓冲帧591B0000 SMBIOS选择iMac19,1（很重要，否则双接口及唤醒始终不正常）VGA（主）+HDMI（副）两个接口工作正常 Platforminfo-ProcessorType-建议1541

硬件配置

硬件	型号	备注

CPU	QL3X(7代魔改U)	显示正常

内存	DDR4 2400	

显卡	HD 630	仿冒HD 530或UHD 630

声卡	ALC662	

网卡	Intel AX200	无线网卡

硬盘	英睿达240G固态	

显示器	LG 27	DP转HDMI

软件版本
OpenCore 0.6.6正式版

安装教程
自己填写一下SMBIOS信息，然后就可以使用了，建议选择iMac19,1 也可以选择iMac18,1-3
因为CPU原因显卡仿冒为HD530,也可以改仿冒UHD630
QL3X魔改CPU，暂时无法睡眠，休眠后开启HDMI显示器不显示，DP转HDMI连接显示器，后面找个DP口显示器再试试。


参考教程
https://github.com/vic-stack/HP-400G3-DM-EFI
https://post.smzdm.com/p/a6lxvzng/
