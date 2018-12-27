# 群命令帮助

# 一些说明
1. QQ号参数可用At来代替
2. 时间参数
	- 纯数字: 记作分钟
	<br> 如 `10` 记作 ”10分钟“
	- 带有字母: d天 h小时 m分钟 s秒
	<br> 如 `1d2h3m4s` 记作 ”1天2小时3分钟4秒“
3. 可用别名来代替这个命令的原始形式
4. 感叹号不区分全角半角
4. 所有命令不区分大小写
5. 所有命令兼容繁体

# 群命令介绍
### !help
- 描述 : 显示机器人帮助链接（即本页面）  
- 默认权限组 : 所有人  
- 用法 : !help

### !sign
- 描述 : 每日签到。
- 默认权限组 : 群员  
- 别名 : 签到
- 权限 : `essential.sign.use`
- 用法 : 
	1.  `!sign`
	2.  腾讯群应用群签到

## !roll
- 描述 : 一个仿osu!里的!roll的一个东西，可以用来模拟掷骰子。  
- 默认权限组 : 群员  
- 别名 : 骰子、色子、投骰子、掷骰子  
- 权限 : `essential.roll.use`
- 用法
	1.  `!roll`
	生成整数 x ∈ [0,9] 
	等价于 !roll 10
	2.  `!roll [整数a]`
	当 x\>0 生成整数 x ∈ [0,a-1]；当x\<0 生成整数 x ∈[a+1,0]；当a=0 生成整数 0
	3.  `!roll [整数a] [整数b]`
	生成整数x∈[a,b-1] (a\<b)

## !money
- 描述 : 经济相关  
- 默认权限组 : 群员  
- 别名 : 余额、金钱  
- 权限 : `essential.money.use`
- 用法
	1.  `!money [无参数]`
	查询自身经济余额
	2.  `!money pay [QQ号] [金钱数量]`
		- 描述 : 转账一定量金钱给你的目标QQ  
		- 默认权限组 : 群员  
		- 别名 : `转账 [QQ号] [金钱数量]`
		- 权限 : `essential.money.pay`
	3.  `!money give [QQ号] [金钱数量]`
		- 描述 : 赠送一定量金钱给你的目标QQ  
		- 默认权限组 : 机器人最高权限  
		- 别名 : `赠送 [QQ号] [金钱数量]`
		- 权限 : `essential.money.admin`

## !profile
- 描述 : 查看用户信息  
- 默认权限组 : 群员  
- 权限 : `essential.user.profile`
- 用法 : 
	1.  `!profile`
	查看自身账号信息
	2.  `!profile [QQ]`
		- 描述 : 查看指定QQ帐户信息  
		- 默认权限组 : 群主  
		- 权限 : `essential.user.info.admin`
	3. `!profile attr`
		- 描述 : 系别设置相关
		- 默认权限组 : 群员
		- 权限 : essential.user.profile.attr.use
	3. `!profile attr set [数字1-5]`
		- 描述 : 系别设置相关 (1寒冰 2烈火 3死亡 4生命 5风暴)
		- 默认权限组 : 群员
		- 权限 : `essential.user.profile.attr.use`

## !marry
- 描述 : 结婚相关 : **发送结婚请求给目标QQ** 或 **接受结婚请求**。
<br>发送结婚请求需要发送者有2000金币并扣除131.4金币。
<br>接收结婚请求需要消耗9金币。
- 默认权限组 : 群员  
- 别名 : 结婚 婚姻系统
- 权限 : `essential.marry.use`  
- 用法 : `!marry [QQ]`

## !divorce
- 描述 : 结婚相关 : 由结婚请求发起者使用本命令。可解除婚姻关系。
- 默认权限组 : 群员  
- 别名 : 离婚
- 权限 : `essential.marry.use`  
- 用法 : `!divorce`

## !music
- 描述 : 使用特性接口点歌，返回第一条搜索结果
例子 :
`!music 54273` (如果搜索字符全是数字的话则使用网易云搜索)
`!music 36019704` (全数字状态下可以使用网易云歌曲编号搜索)
- 默认权限组 : 群员
- 别名 : 点歌、来首、听歌
- 权限 : 
	1.  `essential.music.use` 使用权/默认:群员
	2.  `essential.music.free` 免费使用权/默认:群管
- 用法 : 
	1. `!music [搜索关键字]`

## !mute
- 描述 : 群内禁言指定账户一定时间。  
- 默认权限组 : 群管理员  
- 别名 : 禁言  
- 权限 : `essential.group.admin.mute`
- 用法 : 
	1.  `!mute [QQ] [时长]`
	<br>若时长为0则为解除禁言。
	2.  `!mute 0 1` 全员禁言开。
	3.  `!mute 0 0` 全员禁言关。

## !gmute
- 描述 : 在机器人管理的所有群内禁言指定账户一定的时间  
- 默认权限组 : 机器人管理组  
- 权限 : `essential.admin.mute`
- 用法 : 参数解释同 !mute
	1.  `!gmute [QQ] [时长]`
	2.  `!gmute 0 1`
	3.  `!gmute 0 0`

## !suicide
- 描述 : 顾名思义，一个<s>恶俗</s>自禁言命令。
- 权限 : `essential.suicide.use`
- 默认权限组 : 群员
- 模式组合 :
	- 模式1
		- 描述 : 需要消耗一个 `[Suicide]` 物品。详情请查看商店。  
		- 用法 : `!suicide`
	- 模式2
		- 描述 : 
			- 对于禁言时长做出了最短禁言时长和最大禁言时长的限制。
			- 默认最短时间5分钟 最长时间8小时
		- 用法 : 
			1. `!suicide`
			1. `!suicide [时长]`

## !kick
- 描述 : 把指定人从命令发动群内踢出  
- 默认权限组 : 群管理员  
- 别名 : 踢  
- 权限 : `essential.group.admin.kick`
- 用法 : `!kick [QQ]`

## !gkick
- 描述 : 把指定用户从机器人管理的所有群内踢出  
- 默认权限组 : 机器人管理组  
- 权限 : `essential.admin.kick`
- 用法 : `!gkick [QQ]`

## !ban
- 描述 : 封禁某个账户，把这个账户从本群内踢出且自动拒绝他的加群请求并自动返回指定信息。若理由为空，则默认为 “管理员已拒绝您再次进群”  
- 默认权限组 : 群管理员  
- 权限 : `essential.group.admin.ban`
- 用法 : `!ban [QQ] [理由]`

## !gban
- 描述 : 封禁某个账户，把这个账户从机器人管理的所有群内踢出且自动拒绝他的加群请求并自动返回指定信息。若理由为空，则默认为 “管理员已拒绝您再次进群”  
- 默认权限组 : 机器人管理组  
- 权限 : `essential.admin.ban`
- 用法 : `!gban [QQ] [理由]`


> ## !nick [已取消]
> - 描述 : 按照格式批量修改本群所有人的昵称。格式中必须包含 %NICK% (完全大写) 代表QQ昵称。 如你想添加前缀 “△” 则输入命令 “!nick △%NICK%”  (当然 “!nick↖↗这也是能用的”)  
> - 默认权限组 : 群主  
> - 权限 : 
> 1.  essential.nick.use 使用权/默认:群主
> 2.  essential.nick.passby 绕过修改权/默认:群管
> - 用法 : !nick [格式]
> 
> ## !nicka [已取消]
> - 描述 : 和nick唯一不同的地方是，这是支持正则表达式的。  
> - 默认权限组 : 群主  
> - 权限 : 
> 1.  essential.nicka.use 使用权/默认:群主
> 2.  essential.nick.passby 绕过修改权/默认:群管
> - 用法 : !nick [格式]

!nick 与 !nicka 因腾讯政策限制，现已取消。

## ++
- 描述 : 词语接龙游戏。
- 默认权限组 : 群员  
- 权限 : `game.idiom.query.use`  
- 用法 : 
1.  `++` 查看当前接到的词语
1.  `+++` 查看当前接到的词语
2.  `++ [你的词语]` 接龙

> ## 聊天炸弹 [已取消]
> - 描述 : 如果你发言中包含特定文字则触发奖惩事件。  
> - 默认权限组 : 群员  
> - 权限 : game.chatbomb.query.use  
> - 用法 : 无，被动触发

## !Reciter
- 描述 : 古诗文填空。 
- 默认权限组 : 群员  
- 权限 : 
1.  `game.reciter.query.use` 使用权
2.  `game.reciter.admin` 管理权
3.  `game.reciter.admin.list` 古诗列表
4.  `game.reciter.admin.filter` 筛选器使用权
5.  `game.reciter.answer.use` 答题权
- 用法 : 
1. `!reciter` 查看当前填空的诗句
2. `!reciter on/enable` 开启本功能
3. `!reciter off/disable` 关闭本功能
4. `!reciter list` 查看古诗列表
5. `!reciter filter` 查看本群筛选器
6. `!reciter set` 筛选器字符串
	- 设置本群的古诗筛选器
	- 筛选器规则语法 : 
	- 规则由多个以半角空格分割的古诗编号组成
	- 如果你想能出某一首古诗则在规则里添加你要的古诗编号。
	- 如果你不想出某一首古诗则在规则里添加你不要的古诗编号并在编号前加一个半角减号。
	- 如果你想随便的话，则使用通配符星号。
	- 筛选器匹配规则 :
	- 从你的规则最开始的数字开始匹配，如果找到符合(存在该古诗的编号或者是通配符星号)则合法，如果找到不符合(存在该古诗编号前加半角减号或者是搜索完整条规则都没有这个编号)则不合法。
	- 筛选器例子 :
		- * : 随便一首古诗
		- 0 1 2 3 4 5 6 7 8 9 : 只出现编号为0到9的古诗
		- -0 -1 -2 -3 -4 -5 -6 -7 -8 -9 * : 不出现编号为0到9的古诗

## !quiz
- 测试中的功能。尚有缺陷。
- <img src="https://wx1.sinaimg.cn/large/8ddab624ly1fwzu4luz6oj20f00f0q3k.jpg" width="240"/>

## !Inventory
- 描述 : 背包系统  
- 默认权限组 : 群员  
- 别名 : 背包  
- 权限 : `essential.inventory.use`
- 用法 : 
1. `!inventory` 查看自己背包

## !Auth
- 描述 : 授权系统  
- 默认权限组 : 群员
- 权限 : `essential.auth.use`
- 用法 : 
1. !Auth
	- 描述 : 查看本群的授权信息  
	- 默认权限组 : 群管理  
	- 权限 : `essential.auth.info`
2. !Auth code [授权码] [被授权群号]
!Auth certification [授权码] [被授权群号]
!Auth licence [授权码] [被授权群号]
!Auth license [授权码] [被授权群号]
!Auth code [被授权群号] [授权码]
!Auth certification [被授权群号] [授权码]
!Auth licence [被授权群号] [授权码]
!Auth license [被授权群号] [授权码]
	- 描述 : 使用授权码给某群增加机器人使用期限。本命令不可在控制台群使用。
	- 默认权限组 : 群员
	- 权限 : `essential.auth.code`
3. !Auth give [群号] [时间]
!Auth add [群号] [时间]
!Auth renewal [群号] [时间]
	- 描述 : 给某个群增加一段时间的机器人使用期限。本命令不可在控制台群使用。
	- 默认权限组 : 机器人最高权限
	- 权限 : `essential.auth.admin`
4. !Auth gencode [数量] [时长]
!Auth gencertification [数量] [时长]
!Auth genlicence [数量] [时长]
!Auth genlicense [数量] [时长]
	- 描述 : 生成一定数量一定时长的机器人授权码。本命令不可在控制台群使用。
	- 默认权限组 : 机器人最高权限
	- 权限 : `essential.auth.admin`

## !pixiv [已停用]
- 描述 : P站搜图命令
- 默认权限组 : 群员  
- 权限 : `essential.pixiv.use`
- 用法 : 
	1.  `!pixiv` 随机发送一条搜索结果
	2.  `!pixiv [关键词]` 按照你的关键词搜索并随机发送一张图片
- <img src="https://wx2.sinaimg.cn/large/8ddab624ly1fwzu4lofwbg203o03kwjm.gif" width="240"/>	


## !api
- 描述 : 机器人API工具【使用本功能暂时需要群里的机器人为 梦想码头一号智能姬】
开发文档日后再编辑
- 默认权限组 : 群主
- 权限 : `essential.api.use`
- 用法 : 
1.  `!api create/gen` 删除(如果存在的话)旧的apitoken 并 生成本群的apitoken
2.  `!api del/cancel` 删除本群的apitoken