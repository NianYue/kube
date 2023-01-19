# 简单命令脚本框架

适用于CGA的JS脚本函数封装，整理常用的函数API，帮助大家完成80%的脚本制作和编写，降低调试成本减少出错的风险。


## 设置命令

帮助便捷完成CGA的设置变更，主要控制UI上的功能选项，包括常用的各项设置。 下载后整个文件夹放到与CGAssistant.exe同级目录即可使用封装整理过的函数方法，编写脚本可以参考已有的简单脚本，会逐渐完善。欢迎大家加入一起讨论、完善脚本，我空余有时间也会尽量给大家答疑。

### 1. 设置高速移动 

**功能说明:** 

加速人物走路速度，参数选填，提示超过135%容易掉线 

**参数说明:**

参数1(可选): 移动加速百分比，默认设置130%移动加速

```
示例：
// 移动加速130%
设置高速移动(); 

// 移动加速135%
设置高速移动(135); 
```

### 2. 设置高速采集

**功能说明:**

生产系采集速度增加，参数选填

**参数说明:**

参数1(可选)：采集完成延迟，默认设置4800延迟，过低容易掉线

```
示例：
// 采集延迟4800
设置高速采集(); 

// 采集延迟4500
设置高速采集(4500); 
```

### 3. 设置高速切图

**功能说明:**

跳过切图动画，包括：地图切换、战斗切换等

**参数说明:**

参数1(可选)：默认true开启高速切图，设置false关闭高速切图

```
示例：
// 开启
设置高速切图(); 

// 关闭
设置高速切图(false); 
```

### 4. 设置自动补给

**功能说明:**

对话护士、资深护士会自动补满人物和宠物的血魔，无需手动选择

**参数说明:**

参数1(可选)：默认true开启自动补给，设置false关闭自动补给

```
示例：
设置自动补给(); 
```

### 5. 设置说话防掉线

**功能说明:**

定时发送空字符串的对话内容数据(界面无显示)，防止道具长时间不动掉线

**参数说明:**

参数1(可选)：默认true开启说话防掉线，设置false关闭说话防掉线

```
示例：
设置说话防掉线(); 
```

### 6. 设置自动吃料理

**功能说明:**

开启非战斗自动吃料理功能，身上带的料理满足条件会自动对自己的人物或者宠物使用，目前不支持给队友使用

**参数说明:**

参数1(可选)：默认true开启自动吃料理, false则关闭自动吃料理

参数2(可选)：默认0即目标魔法小于等于0则自动使用料理，支持百分比

参数3(可选)：默认true设置给人物使用料理，false则设置给宠物使用料理

```
示例：
// 魔法小于等于0给人物使用料理
设置自动吃料理(); 

// 魔法小于等于10给人物使用料理
设置自动吃料理(true, 10); 

// 魔法小于等于20%给宠物使用料理
设置自动吃料理(true, '20%', false); 
```

### 7. 设置自动吃血瓶

**功能说明:**

开启非战斗自动吃血瓶功能，身上带的血瓶满足条件会自动对自己的人物或者宠物使用，目前不支持给队友使用

**参数说明:**

参数1(可选)：默认true开启自动吃血瓶, false则关闭自动吃血瓶

参数2(可选): 默认0即目标魔法小于等于0则自动使用血瓶，支持百分比

参数3(可选): 默认true设置给人物使用血瓶，false则设置给宠物使用血瓶

```
示例：
// 魔法小于等于0给人物使用血瓶
设置自动吃血瓶(); 

// 魔法小于等于10给人物使用血瓶
设置自动吃血瓶(true, 10); 

// 魔法小于等于20%给宠物使用血瓶
设置自动吃血瓶(true, '20%', false); 
```

### 8. 设置自动丢弃物品

**功能说明:**

战斗结束自动丢弃的物品列表

**参数说明:**

参数1(可选)：丢弃物品名称列表，默认空数组清空所有丢弃物品，输入必须是全部元素是字符串的数组，例如: ['卡片？','魔石']

参数2(可选): 是否追加物品名称，默认false覆盖模式，true在在已经存在的列表后追加

```
示例：
// 设置战斗结束自动丢弃：卡片？、魔石
设置自动丢弃物品(['卡片？', '魔石']); 

// 追加设置战斗结束自动丢弃：卡片？、魔石、国民衣、国民弓
设置自动丢弃物品(['国民衣', '国民弓'], true); 
```

### 9. 设置自动叠加物品

**功能说明:**

战斗结束自动叠加的物品列表，注意正确配置每样物品的最大叠加数量

**参数说明:**

参数1(可选)：叠加物品名称列表，默认空数组清空所有叠加物品，输入必须是全部元素是字符串的数组，例如: ['地的水晶碎片|999','水的水晶碎片|999']

参数2(可选): 是否追加物品名称，默认false覆盖模式，true在在已经存在的列表后追加

```
示例：
// 设置战斗结束自动叠加：地的水晶碎片、水的水晶碎片
设置自动叠加物品(['地的水晶碎片|999', '水的水晶碎片|999']); 

// 追加设置战斗结束自动丢弃：地的水晶碎片、水的水晶碎片、火的水晶碎片、风的水晶碎片
设置自动叠加物品(['火的水晶碎片|999', '风的水晶碎片|999'], true); 
```

### 10. 设置高速战斗

**功能说明:**

设置是否开启高速战斗，跳过战斗画面，战斗效率提升，同时开启战斗后等待防止掉线

**参数说明:**

参数1(可选)：默认true开启高速战斗，设置false关闭高速战斗

```
示例：
// 开启
设置高速战斗(); 

// 关闭
设置高速战斗(false); 
```

### 11. 设置自动战斗

**功能说明:**

设置是否开启自动战斗，注意需要同时配置战斗条件开启才有效

**参数说明:**

参数1(可选)：默认true开启自动战斗，设置false关闭自动战斗

```
示例：
// 开启
设置自动战斗(); 

// 关闭
设置自动战斗(false); 
```

### 12. 设置自动战斗延迟

**功能说明:**

设置自动战斗延迟，掉线保护功能，一般设置4500毫秒正常不会掉线；战斗延迟是一个时间范围，增加了随机性

**参数说明:**

参数1(可选)：战斗延迟上线，单位毫秒：1秒 = 1000毫秒

```
示例：
// 自动战斗延迟4.0秒~4.5秒
设置自动战斗延迟(4500); 

// 自动战斗延迟3.5秒~4.0秒
设置自动战斗延迟(4000);  
```


### 13. 设置战斗宠物二动

**功能说明:**

设置是否开启自动战斗宠物二动。宠物二行为相同，即两次普通攻、或者使用两次相同的技能

**参数说明:**

参数1(可选)：默认true开启战斗宠物二动，设置false关闭战斗宠物二动

```
示例：
// 开启
设置战斗宠物二动(); 

// 关闭
设置战斗宠物二动(false); 
```


### 14. 设置无限战斗时间

**功能说明:**

战斗倒计时锁定功能，可以实现超长时间的战斗等待，手动多开非常有用的功能

**参数说明:**

参数1(可选)：默认true开启无限战斗时间，设置false关闭无限战斗时间

```
示例：
// 开启
设置无限战斗时间(); 

// 关闭
设置无限战斗时间(false); 
```


### 15. 设置抓宠停止自动战斗

**功能说明:**

遇到1级宠物停止自动战斗，同时播放声音提示

**参数说明:**

参数1(可选)：默认true开启抓宠停止自动战斗，设置false关闭抓宠停止自动战斗

```
示例：
// 开启
设置抓宠停止自动战斗(); 

// 关闭
设置抓宠停止自动战斗(false); 
```

### 16. 设置遇BOSS停止自动战斗

**功能说明:**

遇到BOSS停止自动战斗，同时播放声音提示

**参数说明:**

参数1(可选)：默认true开启遇BOSS停止自动战斗，设置false关闭遇BOSS停止自动战斗

```
示例：
// 开启
设置遇BOSS停止自动战斗(); 

// 关闭
设置遇BOSS停止自动战斗(false); 
```

### 100. 自动寻路

**功能说明:**

自动寻路功能要求当前位置到目标位置的地图已开。如果目标位置是地图切换点，需要设置切图参数。如果是迷宫地图使用，地图刷新会导致寻路失败。

**参数说明:**

参数1(必填)：目标X坐标

参数2(必填): 目标Y坐标

参数3(必填)：默认false达到目标坐标后不切图，true到达目的地切图

返回值1：true寻路成功，false寻路失败

```
示例：
// 移动到坐标(12, 18)
自动寻路(12, 18); 

// 移动到坐标(12, 20)，达到后切换地图
自动寻路(12, 20, true); 
```

### 101. 等待战斗结束

**功能说明:**

暂停脚本继续运行，直到战斗结束

**参数说明:**

参数1(可选)：每次检测的时间间隔(毫秒)，默认3000毫秒检测一次

参数2(可选): 最大检测的次数，默认检测100次，即最多等待3000 * 100 = 300 秒

```
示例：
// 等待战斗结束后返回
等待战斗结束(); 

// 每秒检测一次战斗是否结束，最多检测300次
等待战斗结束(1000, 300); 
```

### 102. 对话NPC

**功能说明:**

与任务NPC对话

**参数说明:**

参数1(必选)：目标NPC的坐标X

参数2(必选): 目标NPC的坐标Y

参数3(可选)：对话选择动作数组，默认空数组[]即不做任何选择，仅发起对话。支持的值 -> '是'|'否'|'下一步'|'确定'|'取消'|

```
示例：
// 对话位置在(46, 9)的NPC，选择是
对话NPC(46, 9, ['是']); 

// 对话位置在(46, 9)的NPC，按顺序选择: 是 -> 下一步 -> 否 -> 确定
对话NPC(46, 9, ['是', '下一步', '否', '确定']); 
```


### 103. 高速遇敌

**功能说明:**

开始在当前位置高速遇敌，内置停止条件检测，目前支持自己血量、魔法、背包数量、受伤情况、队员数量的条件检测。

**参数说明:**

参数1(可选)：保护配置，注意大括号不能少。默认配置和详细解释参考下面
```
{
    min_hp: 1,          // 人物最小生命值，小于等于停止
    min_mp: 0,          // 人物最小魔法值，小于等于停止
    max_injury: 1,      // 人物最大受伤值，受伤或者掉魂停止
    min_pet_hp: 1,      // 宠物最小生命值，小于等于停止
    min_pet_mp: 0,      // 宠物最小魔法值，小于等于停止
    max_item_nums: 21,  // 背包物品最大数量, 默认表示包满不停止
    min_team_nums: 1,   // 队伍最少人数，小于等于停止
}
备注：受伤值含义0正常 1-25(白) 26-50(黄) 51-75(粉) 76-100(红)
```

参数2(可选): 遇敌走路延迟，默认100毫秒。延迟越低遇敌越快，越容易掉线

```
示例：
// 开始高速遇敌，包满停止
高速遇敌({max_item_nums: 20}); 

// 开始高速遇敌，人物生命值<=100，魔法<=30停止遇敌，走路延迟50毫秒
高速遇敌({min_hp: 100, min_mp: 30}, 50); 
```

### 104. 检查当前状态

**功能说明:**

检测当前游戏状态是否出发保护规则，使用需要判断返回结果。

**参数说明:**

参数1(可选)：保护配置，注意大括号不能少。默认配置和详细解释参考下面
```
{
    min_hp: -1,          // 人物最小生命值，小于等于触发
    min_mp: -1,          // 人物最小魔法值，小于等于触发
    max_injury: 999,     // 人物最大受伤值，大于等于触发，掉魂触发
    min_pet_hp: -1,      // 宠物最小生命值，小于等于触发
    min_pet_mp: -1,      // 宠物最小魔法值，小于等于触发
    max_item_nums: 999,  // 背包物品最大数量, 大于等于触发
    min_team_nums: -1,   // 队伍最少人数，小于等于触发
}
备注：受伤值含义0正常 1-25(白) 26-50(黄) 51-75(粉) 76-100(红)
```

返回值1：true表示触发保护规则，false表示触发保护规则

```
示例：
// 如果人物背包中物品数量>=20个，则返回true，否则返回false
检查当前状态({max_item_nums: 20}); 

// 如果人物背包中物品数量>=20个，则返回true，否则返回false
高速遇敌({min_hp: 100, min_mp: 30}, 50); 
```

### 105. 登出回城

**功能说明:**

登出回到城内传送水晶位置，默认登出后延迟1000毫秒返回

**参数说明:**

参数1(可选)：登出后延迟，默认1000毫秒

```
示例：
// 登出
登出回城(); 

// 登出后延迟3000毫秒，即3秒
登出回城(3000);
```

### 106. 登出游戏

**功能说明:**

登出游戏回到区选择画面，例如牧羊，登出后延迟1000毫秒返回

**参数说明:**

参数1(可选)：登出后延迟，默认1000毫秒

```
示例：
// 登出
登出游戏(); 

// 登出后延迟3000毫秒，即3秒
登出游戏(3000);
```

### 107. 自动组队

**功能说明:**

当前坐标位置自动完成组队，队伍列表第一个自动成为队长，全部成员到位返回。队长会自动往旁边走一步、踢出非队伍成员

**参数说明:**

参数1(必填)：队伍成员任务名称的列表，写在最前面的自动成为队长，主要(中括号)和每个人物名称前后(单引号)不要漏

返回值1：true表示组队成功，false表示组队失败

```
示例：
// 人物名称分别是春天(队长)和秋天(队员)组成2人小队
自动组队(['春天', '秋天']); 

// 人物名称分别是(春、夏、秋、冬、雨)组成5人小队，雨是队长
自动组队('雨', '春', '夏', '秋', '冬');
```

### 108. 踢出队伍

**功能说明:**

队长将玩家踢出队伍，队员使用无效。建议使用自动组队，无需直接使用该功能

**参数说明:**

参数1(必填)：踢出队伍的人物名称，注意单引号误漏

参数2(可选)：等待超时，默认5000毫秒

返回值1：true表示踢出玩家成功，false表示踢出玩家失败

```
示例：
// 将玩家 -> 风花雪月 <-踢出队伍
踢出队伍('风花雪月'); 
```

### 109. 加入队伍

**功能说明:**

作为队员加入队伍。建议使用自动组队，无需直接使用该功能

**参数说明:**

参数1(必填)：队长名称

参数2(可选)：等待超时，默认5000毫秒

返回值1：true表示加入成功，false表示加入失败

```
示例：
// 加入玩家 -> 让子弹飞 <- 的队伍
加入队伍('让子弹飞'); 
```

### 110. 自动贩卖

**功能说明:**

自动贩卖物品，需要人物走到贩卖NPC附近

**参数说明:**

参数1(必填)：贩卖NPC坐标X

参数2(必填)：贩卖NPC坐标Y

参数3(可选)：贩卖的物品名称，默认['魔石', '卡片？']

参数4(可选)：等待超时，默认5000毫秒

```
示例：
// 向位于坐标(19,22)NPC贩卖所有魔石、水龙的卡片
自动贩卖(19, 22, ['魔石', '水龙的卡片']);
```