1. 
	- 找到Magisk
	- 找到被Magisk模块修改的
	- 找到su进程
	- 找到可执行程序"su"
		- 面具-设置-隐藏Magisk应用。
		- 部分面具模块问题，自行关闭重启排查。
		- 面具-配置排除列表-勾选momo(全选)。
		- 看看你面具处于白名单还是黑名单，白名单选择APP会获取root权限的（比如爱玩机、墨•状态栏）这些。黑名单选择需要隐藏应用的应用（比如Q、W）
		- 白名单需要用隐藏应用列表APP，Lsp管理器勾选隐藏应用列表，隐藏应用列表APP配置，模板配置-创建黑名单模板-
			- 应用不可见（选择模块之类）
			- 已应用于…个应用（选择对其隐藏的APP）成品模板在末尾链接，然后对momo启用黑名单。
		- 确保Shamiko模块正常工作(笑脸而非红X图标)。
		- 是否开了遵守排除列表？关闭后重启即可解决。
		- Shamiko非笑脸，是红X图标？移除Shamiko模块重启，重装再重启。
2. 
	- 找到Zygisk
	- Zygote被注入
	- Zygote行为异常
		- 更新Shamiko模块_0.6+以上版本。
		- 更新模块和面具+Momo
3. 
	- 发现注入代码
		- 安装高于4.3.1版本的Momo软件。
		- 更新Momo和面具
4. 
	- ART参数异常
	- SElinux处于宽容模式
	- Seccomp未开启
		- 移除火柴的防格机模块或者删除Fake Location
		- Fake Location会让你的手机非SDK接口的限制失效SElinux宽容模式、权限系统异常
		- 官方GG修改器-修复-(切换到工作，而SeLinux，并重新启动应用程序)，
		- 更换使用官方GG修改器，魔改GG自查看作者是否移除了"修复"按钮。
		- 排查面具模块，关闭或移除后重启系统，
		- 排除常住后台自启动需授权root的应用。
		- 可尝试安装：开启SELinux.zip 面具模块
5. 
	- SElinux规则异常，允许了neverallow条目
		- 线刷回官方系统
6. 
	- 数据未加密，挂载参数被修改
		- 第三方ROM，请线刷回官方系统。
7. 
	- 找到Xposed框架
		- 卸载Xposed、Edxposed，更换使用LSPosed。
8. 
	- 找到Riru
	- Momo环境损坏/无响应
		- 更新面具25.2以上版本，使用Zygisk模块。
		- 23.0面具已是过时产物，放弃使用Riru模块
		- 更新Momo更新面具软件，或者删除Riru安装Zygisk
9. 
	- init.rc被修改
		- 第三方recovery引起的问题，
		- 更换其他的三方rec或刷回官方rec。
		- 或者安装：隐藏init.rc被发现.zip 面具模块
10. 
	- 分区挂载异常
		- SYSTEM分区被解锁，可能与boot修补magisk时保留了(AVB2.0/dm-verity)有关。
		- 如果是安卓10及以下安卓版本系统那请无视此项问题。
		- 安卓11请线刷回官方系统，若是官方系统解锁SYSTEM分区，卡刷一次当前系统ROM包可恢复
		- 如果使用的不是官方系统，官改默认解锁SYSTEM分区可以无视，或者线刷回官方系统。
		- 此问题不是啥大问题(不影响你隐藏的环境)，你爱管不管都行。
11. 
	- 设备正在使用非原厂系统
		- 字面意思，无需解释，线刷回官方系统。
		- 刷会默认官方系统（版本无所谓），官改系统会报错
12. 
	- 包管理服务异常
		- 卸载或关闭与核心破解类似的软件
		- 关闭核心破解第二项（禁用软件包管理器签名验证），重启
13. 
	- 权限系统异常
		- 卸载或关闭与核心破解类似的软件
		- 卸载 幸运破解器
		- 卸载 Fake Location
14. 
	- 处于调试环境
		- /system/build.prop路径内build.prop文件内ro.debuggable=1必须＝0 ＝1必出现。
		- 关闭面具模块重启，排查是否模块问题。
		- (可将其修改为0保存重启手机，未解锁SYSTEM分区不适用此方法，会提示分区挂载读写失败。)
		- 随便找一个面具模块，在面具模块的system.prop文件内加入：ro.debuggable=0 并保存注意不要填成 (# ro.debuggable=0)加#为注释信息，不会对其生效。面具刷入这个修改过的模块重启即可解决。
15. 
	- 已开启调试模式
		- 关闭所有/USB/无线/调试/选项后再关闭开发者模式。
		- 关闭USB、WiFi、调试然后关闭开发者，如需开发者选项就重启，在打开开发者模式如果还显示报错就刷末尾模块
16. 
	- 存在Magisk或TWRP特定文件
		- 删除以下文件夹：
			/sdcard/TWRP
			/sdcard/Fox
			你每进一次第三方Rec都会重新生成此文件夹。
		- 如果你用的是/skkk/mi_block/小米奇迹/的twrp，可以去twrp内，高级-更改TWRP文件夹修改为非twrp的命名。
		- 如果没有则代表你的twrp版本不是3.7.x以上。
		- 可在酷安搜索用户：mi_block 下载最新版本twrp。
		- skkk的twrp高于3.7版本不会创建TWRP文件夹，无需更改。
17. 
	- 非SDK接口的限制失效
		一般是Fake Location引起，卸载Fake Location
		解决方法:解决非SDK接口限制失效问题
		mt管理器创建一个.sh文件，粘贴↓进去，root执行
		
		su2
		settings delete global hidden_api_policy
		settings delete global hidden_api_policy_p_apps
		settings delete global hidden_api_policy_pre_p_apps
		settings delete global hidden_api_blacklist_exe
	- 如果权限不够就开777权限，火力全开。
		这个代码不行的话就用爱玩机打开一个终端然后输入
		settings delete global hidden_api_policy
		
		settings delete global hidden_api_policy_p_apps
		
		settings delete global hidden_api_policy_pre_p_apps
		
		settings delete global hidden_api_blacklist_exemptions
		
		勾选✓root，▷执行。
		或者使用 "解决非SDK接口限制失效(解压).zip" 解决。
18. 
	- bootloader未锁定/TEE损坏
		并不会影响正常使用，检测root的应用不会检测