检测详细报错含义:
1. Normal
	 - 本地测试通过！
2. Abnormal Environment
	- 已找到Magisk/KSU/APatch或找到lsp
	- 目前狐狸没办法过这一点
	- 附Conventional Tests (1)
	- 弱bl，hide或者shamiko可以解决
3. Conventional Tests
	- (2)
		- 己找到magisk或ksu或APatch
		- ksu关闭卸载模块导致或其他
	- (3)
		- ksu没安装shamiko导致或其他
	- (4)
		- 安卓15
		- 目前狐狸无法过这一条
		- 找到metadata路径magisk文件夹删除即可
		- 面具版本需要28102及以上
	- (6)
		- 超级逆天环境
		- 已获取到root权限
	- (8)
		- 密钥已解锁刷tricky store或密钥已吊销
	- (9)
		- 已解锁bootloader
		- 密钥己解锁
	- (10)
		- 第三方ROM
	- (18)
		- 已解锁bootloader（类原生）
		- 第三方ROM
	- (1a)
		- ？
	- (1e)
		- 已解锁bootloader
		- 第三方ROM
		- 已找到Magisk
	- (a)
		- 异常环境
		- 检测到Bootloader Spoofer xp模块欺骗
	- (c)
		- 安卓15
		- 找到metadata magisk+密钥己解锁
	- (d)
		- 安卓15
		- 密钥己解锁+已解锁bootloader
		- 找到metadata magisk
	-  (e)
		- 密钥己解锁
		- 己获取root权限
		- 超级逆天环境
		- 已找到Magisk
		- RVX模块？
	- (f)
		- 己获取root权限
		- 超级逆天环境
		- 已解锁bootloader
		- 密钥己解锁
		- 已找到Magisk
4. Evil Service 
	- (1)
		- 墓碑相关或注入问题或隐藏应用列表版本太低
	- (2)
		- LSPosed已找到或相关问题
	- (3)
		- LSPosed已找到或相关问题
	- (4)
		- Shamiko找到了？
	- (6)
		- 找到注入服务？
5. Found Hook
	- 找到LSPosed模块hook
6. Found Injection（包括04）
	- 已找到Zygisk或ZygiskNext（更新zygisk next1.2.7）
7. Futile Hide
	- (01)
		- 检测到zygisk next已开启遵守排除列表
	- (02)
		- Zygisk-Assistant 在 Kitsune（检查隐藏模块）
	-  (04)
		- 找到内核模块Cherish Peakaboo KPM或别的模块导致
		- 使用cherish_peekaboo_1.5 KPM可以过
	- (08)
		- KSU Umount / zygisk-detach / 狐狸有些正常模块会爆08（兼容差）/存储空间隔离模块
	- (09)
		- ？
	-  (10)
		- 找到lsp特征文件
	- (14)
		- 找到lsp特征文件加找到内核模块
	- (0a)
		- 检测到Magisk排除列表
	- (0b)
		- ？
8. Inconsistent Mount
	- 发现模块修改/系统（检查模块）
9. Partition Check Fail
	- boot分区效验失败！
	- ro.boot.vbmeta.digest无效
10. Property Modified
	- (01)
		- 系统属性被修改，例如分区效验
	- (07)
		- 修改了序列号？
	- (08)
		- 系统属性被修改，例如分区效验
	- (10)
		- 已执行resetprop--delete命令（检查模块或官改）例如改机型
	- (30)
		- 模块导致或官改
11. Permission Loophole
	- 策略设置不正确，建议使用较新版本的ROOT管理器
	- 或潘多拉之类的调度内核或宽容模式
12. Something wrong (999)
	- 内部应用程序错误，关闭隐藏应用列表Vold data 隔离
13. Tampered Attestation Key
	- keybox失效或检查到key修改
	- 小米红米tee损坏机型 需要修复
14. Partition Modified
	- 禁用avb校验导致（重设哈希值可以解决）
15. Suspicious Surrounding
	- 原因未知，普遍在apatch next开了排除修改出现
	- 开启默认卸载模块