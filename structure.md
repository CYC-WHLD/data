# 數據包結構說明

本文件描述了Minecraft數據包的工作區結構，使用繁體中文進行說明。每個檔案和目錄的功能將在後面詳細列出。

## 整體結構

```
datapacks/
├── README.md
├── build_height/
│   ├── pack.mcmeta
│   └── data/
│       └── minecraft/
│           └── dimension_type/
│               ├── overworld_caves.json
│               └── overworld.json
└── for308/
    ├── pack.mcmeta
    ├── .vscode/
    │   └── settings.json
    └── data/
        ├── 308/
        │   ├── advancement/
        │   │   ├── chundo_man.json  # 成都市長：控制操縱桿300次
        │   │   ├── chundo_master.json  # 成都超人：控制操縱桿1000次
        │   │   ├── chundo.json  # 成都人：控制操縱桿50次
        │   │   ├── copper.json  # 全民大煉銅：知道怎麼練銅
        │   │   ├── exppp_god.json  # 我獨自八七：達到187等，你要這麼多經驗值幹啥？
        │   │   ├── exppp_master.json  # 我獨自升級：達到100等
        │   │   ├── exppp.json  # 大撒幣：贈送他人3000點經驗值
        │   │   ├── lever.json  # 隱藏進度：使用拉桿
        │   │   ├── repulse.json  # 有沒有注意看訊息？：您怎麼已讀別人的tpa請求？
        │   │   ├── start.json  # 起點－－八班－－
        │   │   ├── death/
        │   │   │   ├── 2.json
        │   │   │   ├── 3.json
        │   │   │   ├── 4.json
        │   │   │   └── dog.json
        │   │   ├── entity/
        │   │   │   ├── ghast.json
        │   │   │   ├── kill_horse.json
        │   │   │   └── zhang.json
        │   │   ├── fight/
        │   │   │   ├── clown.json
        │   │   │   ├── clown_fish.json
        │   │   │   ├── god.json
        │   │   │   └── heavy.json
        │   │   ├── fish/
        │   │   │   ├── fish.json
        │   │   │   ├── fish_cook.json
        │   │   │   ├── fly_fish.json
        │   │   │   ├── fly_fish_pro.json
        │   │   │   ├── horn.json
        │   │   │   └── light.json
        │   │   ├── forge/
        │   │   ├── main/
        │   │   ├── medical/
        │   │   ├── times/
        │   │   │   └── decade.json
        │   │   ├── use/
        │   │   └── walk/
        │   │       ├── 1.json
        │   │       ├── 2.json
        │   │       ├── 3.json
        │   │       ├── 64.json
        │   │       ├── ccp.json
        │   │       ├── nonono.json
        │   │       └── smmw.json
        │   ├── damage_type/
        │   │   └── player_attack_ex.json  # 玩家攻击扩展 - 自定义玩家伤害类型
        │   ├── datapack/
        │   ├── dialog/
        │   │   ├── exp_menu.json  # 經驗值銀行 - 经验值存取菜单
        │   │   ├── give_bu.json  # 赠送菜单 - 经验值赠送界面
        │   │   ├── olduseful.json  # 旧实用功能 - 已弃用菜单
        │   │   ├── phiz.json  # 表情菜单 - 表情符号选择
        │   │   ├── team_set.json  # 队伍设置 - 队伍配置菜单
        │   │   ├── team.json  # 隊伍菜單 - 队伍管理、创建、邀请
        │   │   ├── tpa.json  # 传送请求菜单 - TPA邀请界面
        │   │   ├── tpayesno.json  # 传送确认 - 是/否确认菜单
        │   │   └── useful.json  # 實用功能 - 天气、时间、展示框、头颅查询
        │   ├── dimension/
        │   ├── dimension_type/
        │   ├── enchantment/
        │   │   ├── poison.json  # 劇毒 - 造成中毒效果(2-4级,50-200刻)
        │   │   ├── tetanus.json  # 破傷風 - 造成中毒和凋零效果
        │   │   └── tool/
        │   ├── enchantment_provider/
        │   ├── function/
        │   │   ├── adv.mcfunction  # 广告发送 - 向全体玩家发送存储中的广告信息
        │   │   ├── load.mcfunction  # 初始化加载 - 设置计分板、版本、缓存和基本游戏统计
        │   │   ├── sec.mcfunction  # 每秒执行 - 植物操作、生物召唤、广告轮播
        │   │   ├── tick.mcfunction  # 每刻执行 - 调用玩家/生物/建筑刻事件及秒计数器
        │   │   ├── build/
        │   │   │   ├── anvil/
        │   │   │   │   ├── operate/
        │   │   │   │   │   ├── anvil.mcfunction
        │   │   │   │   │   ├── flaming.mcfunction
        │   │   │   │   │   └── title.mcfunction
        │   │   │   │   └── title/
        │   │   │   │       ├── fail.mcfunction
        │   │   │   │       ├── indoor.mcfunction
        │   │   │   │       ├── learner.mcfunction
        │   │   │   │       ├── master.mcfunction
        │   │   │   │       ├── noob.mcfunction
        │   │   │   │       └── pro.mcfunction
        │   │   │   ├── goldenclock/
        │   │   │   │   ├── fall.mcfunction
        │   │   │   │   ├── grow.mcfunction
        │   │   │   │   ├── growmuj.mcfunction
        │   │   │   │   └── operating.mcfunction
        │   │   │   ├── griner/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   ├── debug.mcfunction
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   ├── fail.mcfunction
        │   │   │   │   ├── fail_b.mcfunction
        │   │   │   │   ├── inter.mcfunction
        │   │   │   │   ├── interact_set.mcfunction
        │   │   │   │   ├── main.mcfunction
        │   │   │   │   ├── operating.mcfunction
        │   │   │   │   ├── inter/
        │   │   │   │   │   ├── dialog.mcfunction
        │   │   │   │   │   ├── hit.mcfunction
        │   │   │   │   │   ├── tele.mcfunction
        │   │   │   │   │   ├── test_tele.mcfunction
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   ├── gr1/
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   ├── gr2/
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   ├── gr3/
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   ├── main/
        │   │   │   │   │   ├── back.mcfunction
        │   │   │   │   │   ├── finish.mcfunction
        │   │   │   │   │   ├── trigger.mcfunction
        │   │   │   │   │   └── settlement/
        │   │   │   │   │       ├── handle/
        │   │   │   │   │       │   ├── bamboo.mcfunction
        │   │   │   │   │       │   ├── bone.mcfunction
        │   │   │   │   │       │   ├── emerald.mcfunction
        │   │   │   │   │       │   ├── log.mcfunction
        │   │   │   │   │       │   ├── nautilus_shell.mcfunction
        │   │   │   │   │       │   ├── resin_brick.mcfunction
        │   │   │   │   │       │   ├── string.mcfunction
        │   │   │   │   │       │   ├── stripped_cherry_log.mcfunction
        │   │   │   │   │       │   ├── stripped_crimson_stem.mcfunction
        │   │   │   │   │       │   ├── stripped_warped_stem.mcfunction
        │   │   │   │   │       │   └── type/
        │   │   │   │   │       │       ├── dagger.mcfunction
        │   │   │   │   │       │       ├── greatsword.mcfunction
        │   │   │   │   │       │       ├── katana.mcfunction
        │   │   │   │   │       │       ├── rapier.mcfunction
        │   │   │   │   │       │       ├── sickle.mcfunction
        │   │   │   │   │       │       ├── spear.mcfunction
        │   │   │   │   │       │       └── sword.mcfunction
        │   │   │   │   │       ├── level.mcfunction
        │   │   │   │   │       ├── lore2.mcfunction
        │   │   │   │   │       ├── lore3.mcfunction
        │   │   │   │   │       ├── named.mcfunction
        │   │   │   │   │       ├── named2.mcfunction
        │   │   │   │   │       ├── storein.mcfunction
        │   │   │   │   │       ├── storelore.mcfunction
        │   │   │   │   │       ├── sword.mcfunction
        │   │   │   │   │       └── handle/
        │   │   │   │   │           ├── bamboo.mcfunction
        │   │   │   │   │           ├── bone.mcfunction
        │   │   │   │   │           ├── emerald.mcfunction
        │   │   │   │   │           ├── log.mcfunction
        │   │   │   │   │           ├── nautilus_shell.mcfunction
        │   │   │   │   │           ├── resin_brick.mcfunction
        │   │   │   │   │           ├── string.mcfunction
        │   │   │   │   │           ├── stripped_cherry_log.mcfunction
        │   │   │   │   │           ├── stripped_crimson_stem.mcfunction
        │   │   │   │   │           └── stripped_warped_stem.mcfunction
        │   │   │   │   ├── pot/
        │   │   │   │   │   ├── trigger.mcfunction
        │   │   │   │   │   └── add/
        │   │   │   │   │       ├── oil1.mcfunction
        │   │   │   │   │       └── oil2.mcfunction
        │   │   │   │   │       └── water.mcfunction
        │   │   │   │   ├── settlement/
        │   │   │   │   │   ├── trigger.mcfunction
        │   │   │   │   │   ├── knife/
        │   │   │   │   │   │   ├── check.mcfunction
        │   │   │   │   │   │   ├── fail.mcfunction
        │   │   │   │   │   │   ├── lvl.mcfunction
        │   │   │   │   │   │   └── success.mcfunction
        │   │   │   │   │   └── quen/
        │   │   │   │   │       ├── dbt.mcfunction
        │   │   │   │   │       ├── fail.mcfunction
        │   │   │   │   │       ├── miss.mcfunction
        │   │   │   │   │       ├── named.mcfunction
        │   │   │   │   │       ├── named2.mcfunction
        │   │   │   │   │       ├── success.mcfunction
        │   │   │   │   │       ├── water_break.mcfunction
        │   │   │   │   │       └── over/
        │   │   │   │   │           ├── check.mcfunction
        │   │   │   │   │           ├── fail.mcfunction
        │   │   │   │   │           ├── ful_success.mcfunction
        │   │   │   │   │           └── success.mcfunction
        │   │   │   │   └── start/
        │   │   │   │       ├── knife.mcfunction
        │   │   │   │       └── uziron.mcfunction
        │   │   │   │       └── operate/
        │   │   │   │           ├── anvil.mcfunction
        │   │   │   │           ├── flaming.mcfunction
        │   │   │   │           └── title.mcfunction
        │   │   │   │           └── title/
        │   │   │   │               ├── fail.mcfunction
        │   │   │   │               ├── indoor.mcfunction
        │   │   │   │               ├── learner.mcfunction
        │   │   │   │               ├── master.mcfunction
        │   │   │   │               ├── noob.mcfunction
        │   │   │   │               └── pro.mcfunction
        │   │   │   ├── muj/
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   └── fail.mcfunction
        │   │   │   ├── nmuj/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   ├── fail.mcfunction
        │   │   │   │   ├── fail2.mcfunction
        │   │   │   │   ├── inter.mcfunction
        │   │   │   │   ├── main.mcfunction
        │   │   │   │   ├── operating.mcfunction
        │   │   │   │   ├── updata.mcfunction
        │   │   │   │   ├── burn/
        │   │   │   │   │   └── did.mcfunction
        │   │   │   │   └── inter/
        │   │   │   │       ├── broke.mcfunction
        │   │   │   │       └── collected.mcfunction
        │   │   │   │       └── trigger.mcfunction
        │   │   │   ├── replicater/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   ├── debug.mcfunction
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   ├── fail.mcfunction
        │   │   │   │   ├── fail2.mcfunction
        │   │   │   │   ├── fail_b.mcfunction
        │   │   │   │   ├── inter.mcfunction
        │   │   │   │   ├── item.mcfunction
        │   │   │   │   ├── main.mcfunction
        │   │   │   │   ├── operating.mcfunction
        │   │   │   │   ├── out_fuel.mcfunction
        │   │   │   │   ├── did/
        │   │   │   │   │   ├── book.mcfunction
        │   │   │   │   │   ├── copy.mcfunction
        │   │   │   │   │   ├── out.mcfunction
        │   │   │   │   │   ├── repair_test.mcfunction
        │   │   │   │   │   ├── shutdown.mcfunction
        │   │   │   │   │   ├── spearing.mcfunction
        │   │   │   │   │   ├── stack.mcfunction
        │   │   │   │   │   └── totem.mcfunction
        │   │   │   │   └── inter/
        │   │   │   │       ├── fuel.mcfunction
        │   │   │   │       ├── put_item.mcfunction
        │   │   │   │       ├── take_item.mcfunction
        │   │   │   │       ├── tele.mcfunction
        │   │   │   │       └── use.mcfunction
        │   │   │   │       └── trigger.mcfunction
        │   │   │   ├── rf/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   ├── fail.mcfunction
        │   │   │   │   ├── fail_b.mcfunction
        │   │   │   │   ├── flaming.mcfunction
        │   │   │   │   ├── inter.mcfunction
        │   │   │   │   ├── interact_set.mcfunction
        │   │   │   │   ├── main.mcfunction
        │   │   │   │   ├── operating.mcfunction
        │   │   │   │   ├── out_fuel.mcfunction
        │   │   │   │   ├── rein.mcfunction
        │   │   │   │   ├── rein2.mcfunction
        │   │   │   │   ├── inter/
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   │   ├── load/
        │   │   │   │   │   │   ├── en.mcfunction
        │   │   │   │   │   │   ├── fuel.mcfunction
        │   │   │   │   │   │   ├── metiral.mcfunction
        │   │   │   │   │   │   ├── nether.mcfunction
        │   │   │   │   │   │   ├── oil.mcfunction
        │   │   │   │   │   │   ├── pn.mcfunction
        │   │   │   │   │   │   ├── ppn.mcfunction
        │   │   │   │   │   │   ├── start_oil.mcfunction
        │   │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   │   └── out/
        │   │   │   │   │       ├── oil.mcfunction
        │   │   │   │   │       └── trigger.mcfunction
        │   │   │   ├── tp_port/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   │   ├── fail.mcfunction
        │   │   │   │   │   ├── fail2.mcfunction
        │   │   │   │   │   ├── fail_b.mcfunction
        │   │   │   │   │   ├── inter.mcfunction
        │   │   │   │   │   ├── main.mcfunction
        │   │   │   │   │   ├── operating.mcfunction
        │   │   │   │   │   ├── out_fuel.mcfunction
        │   │   │   │   │   ├── inter/
        │   │   │   │   │   │   ├── dialog.mcfunction
        │   │   │   │   │   │   ├── fuel.mcfunction
        │   │   │   │   │   │   ├── tele.mcfunction
        │   │   │   │   │   │   ├── test_tele.mcfunction
        │   │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   │   └── starttp/
        │   │   │   │   │       ├── be_called.mcfunction
        │   │   │   │   │       ├── brige.mcfunction
        │   │   │   │   │       ├── call_down.mcfunction
        │   │   │   │   │       ├── finish.mcfunction
        │   │   │   │   │       ├── particle_x.mcfunction
        │   │   │   │   │       ├── particle_y.mcfunction
        │   │   │   │   │       ├── preparation.mcfunction
        │   │   │   │   │       ├── reciprocal.mcfunction
        │   │   │   │   │       └── spread.mcfunction
        │   │   │   ├── tp_stone/
        │   │   │   │   ├── check.mcfunction
        │   │   │   │   ├── construct.mcfunction
        │   │   │   │   ├── destruct.mcfunction
        │   │   │   │   ├── fail.mcfunction
        │   │   │   │   ├── fail2.mcfunction
        │   │   │   │   ├── fail_b.mcfunction
        │   │   │   │   ├── inter.mcfunction
        │   │   │   │   ├── main.mcfunction
        │   │   │   │   ├── operating.mcfunction
        │   │   │   │   ├── out_fuel_loop.mcfunction
        │   │   │   │   ├── inter/
        │   │   │   │   │   ├── dialog.mcfunction
        │   │   │   │   │   ├── fuel.mcfunction
        │   │   │   │   │   ├── tele.mcfunction
        │   │   │   │   │   ├── test_tele.mcfunction
        │   │   │   │   │   └── trigger.mcfunction
        │   │   │   │   └── starttp/
        │   │   │   │       ├── be_called.mcfunction
        │   │   │   │       ├── brige.mcfunction
        │   │   │   │       ├── call_down.mcfunction
        │   │   │   │       ├── finish.mcfunction
        │   │   │   │       ├── particle_x.mcfunction
        │   │   │   │       ├── particle_y.mcfunction
        │   │   │   │       ├── preparation.mcfunction
        │   │   │   │       ├── reciprocal.mcfunction
        │   │   │       └── spread.mcfunction
        │   │   │   └── vault/
        │   │   │       ├── fail.mcfunction
        │   │   │       └── operating.mcfunction
        │   │   ├── mob/
        │   │   │   ├── q.mcfunction
        │   │   │   ├── summon.mcfunction
        │   │   │   ├── tick.mcfunction
        │   │   │   ├── bug/
        │   │   │   │   └── spread.mcfunction
        │   │   │   │   ├── elite/
        │   │   │   │   │   ├── bug.mcfunction
        │   │   │   │   │   ├── x2.mcfunction
        │   │   │   │   │   └── x3.mcfunction
        │   │   │   │   └── pro/
        │   │   │   │       ├── lurker/
        │   │   │   │       │   ├── did.mcfunction
        │   │   │   │       │   └── pro.mcfunction
        │   │   │   │       └── mother/
        │   │   │   │           ├── did.mcfunction
        │   │   │   │           └── pro.mcfunction
        │   │   │   ├── creeper/
        │   │   │   │   ├── spread.mcfunction
        │   │   │   │   ├── spread1.mcfunction
        │   │   │   │   ├── spread2.mcfunction
        │   │   │   │   ├── elite/
        │   │   │   │   │   └── creeper.mcfunction
        │   │   │   │   └── pro/
        │   │   │   │       ├── flast/
        │   │   │   │       │   ├── summon.mcfunction
        │   │   │   │       │   └── summon2.mcfunction
        │   │   │   │       └── nucker/
        │   │   │           ├── summon.mcfunction
        │   │   │           └── summon2.mcfunction
        │   │   │   ├── illager/
        │   │   │   │   └── warden.mcfunction
        │   │   │   ├── special/
        │   │   │   │   ├── warden.mcfunction
        │   │   │   │   └── witch.mcfunction
        │   │   │   └── undead/
        │   │   │       ├── spread.mcfunction
        │   │   │       ├── elite/
        │   │   │       │   ├── undead.mcfunction
        │   │   │       │   ├── x2.mcfunction
        │   │   │       │   └── x3.mcfunction
        │   │   │       └── pro/
        │   │   │           ├── army/
        │   │   │           │   ├── did.mcfunction
        │   │   │           │   ├── pro.mcfunction
        │   │   │           │   └── promax.mcfunction
        │   │   │           ├── cavalry/
        │   │   │           │   ├── did.mcfunction
        │   │   │           │   ├── pro.mcfunction
        │   │   │           │   └── promax.mcfunction
        │   │   │           └── desert/
        │   │   │               ├── did.mcfunction
        │   │   │               ├── pro.mcfunction
        │   │   │               └── promax.mcfunction
        │   │   └── player/
        │   │       ├── chundo.mcfunction
        │   │       ├── create_account.mcfunction
        │   │       ├── death.mcfunction
        │   │       ├── death_oper.mcfunction
        │   │       ├── ench.mcfunction
        │   │       ├── exp.mcfunction
        │   │       ├── fish.mcfunction
        │   │       ├── getid.mcfunction
        │   │       ├── ghast.mcfunction
        │   │       ├── give_bundle.mcfunction
        │   │       ├── kill_villager.mcfunction
        │   │       ├── loaddata.mcfunction
        │   │       ├── menu.mcfunction
        │   │       ├── potion.mcfunction
        │   │       ├── sec.mcfunction
        │   │       ├── sign.mcfunction
        │   │       ├── tick.mcfunction
        │   │       ├── walk.mcfunction
        │   │       ├── clock/
        │   │       │   ├── hour.mcfunction
        │   │       │   ├── min.mcfunction
        │   │       │   └── sec.mcfunction
        │   │       ├── exp/
        │   │       │   ├── all_save.mcfunction
        │   │       │   ├── count.mcfunction
        │   │       │   ├── count_exp.mcfunction
        │   │       │   ├── fail.mcfunction
        │   │       │   ├── get.mcfunction
        │   │       │   ├── menu.mcfunction
        │   │       │   ├── pass.mcfunction
        │   │       │   ├── save.mcfunction
        │   │       │   ├── save_some.mcfunction
        │   │       │   ├── take_out.mcfunction
        │   │       │   ├── tellaw.mcfunction
        │   │       │   ├── dialog/
        │   │       │   │   ├── get.mcfunction
        │   │       │   │   ├── gift.mcfunction
        │   │       │   │   └── save.mcfunction
        │   │       │   ├── formula/
        │   │       │   │   ├── 1.mcfunction
        │   │       │   │   ├── 2.mcfunction
        │   │       │   │   └── 3.mcfunction
        │   │       │   └── give/
        │   │       │       ├── conversion.mcfunction
        │   │       │       ├── exe.mcfunction
        │   │       │       ├── loop.mcfunction
        │   │       │       ├── pass.mcfunction
        │   │       │       ├── storage.mcfunction
        │   │       │       ├── summon_exp.mcfunction
        │   │       │       ├── summon_id.mcfunction
        │   │       │       ├── tick.mcfunction
        │   │       │       ├── trigger.mcfunction
        │   │       ├── fireball/
        │   │       │   ├── did.mcfunction
        │   │       │   ├── spread.mcfunction
        │   │       │   └── summon.mcfunction
        │   │       ├── forge/
        │   │       │   ├── get_data.mcfunction
        │   │       │   ├── get_data_sto.mcfunction
        │   │       │   ├── menu.mcfunction
        │   │       │   ├── test/
        │   │       │   │   ├── knife.mcfunction
        │   │       │   │   ├── metiral.mcfunction
        │   │       │   │   ├── minus.mcfunction
        │   │       │   │   ├── operation.mcfunction
        │   │       │   │   └── uziron.mcfunction
        │   │       ├── medical/
        │   │       │   ├── damage.mcfunction
        │   │       │   ├── damage_s.mcfunction
        │   │       │   ├── song.mcfunction
        │   │       │   ├── tick.mcfunction
        │   │       │   ├── adrenaline/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── effect.mcfunction
        │   │       │   │   ├── effect_o.mcfunction
        │   │       │   │   ├── fail.mcfunction
        │   │       │   │   ├── fail_s.mcfunction
        │   │       │   │   ├── test.mcfunction
        │   │       │   ├── antibiotic/
        │   │       │   │   └── tick.mcfunction
        │   │       │   ├── aspirin/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── d/
        │   │       │   ├── debuff/
        │   │       │   │   ├── dark.mcfunction
        │   │       │   │   ├── deathness.mcfunction
        │   │       │   │   ├── diding.mcfunction
        │   │       │   │   ├── heavy.mcfunction
        │   │       │   │   ├── light.mcfunction
        │   │       │   │   ├── medal.mcfunction
        │   │       │   ├── heroin/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── effect.mcfunction
        │   │       │   │   └── least.mcfunction
        │   │       │   ├── methadone/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── mujcookie/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── effect.mcfunction
        │   │       │   │   └── least.mcfunction
        │   │       │   ├── naloxone/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── pipe/
        │   │       │   │   ├── add.mcfunction
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── add/
        │   │       │   │   │   ├── muj.mcfunction
        │   │       │   │   │   └── opium.mcfunction
        │   │       │   │   ├── muj/
        │   │       │   │   │   ├── did.mcfunction
        │   │       │   │   │   ├── effect.mcfunction
        │   │       │   │   │   └── least.mcfunction
        │   │       │   │   └── opium/
        │   │       │   │       ├── did.mcfunction
        │   │       │   │       ├── effect.mcfunction
        │   │       │   │       └── least.mcfunction
        │   │       │   ├── syringe/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── perry.mcfunction
        │   │       │   │   ├── heroin/
        │   │       │   │   │   ├── did.mcfunction
        │   │       │   │   │   ├── effect.mcfunction
        │   │       │   │   │   ├── effect_o.mcfunction
        │   │       │   │   │   └── test.mcfunction
        │   │       │   │   ├── morphine/
        │   │       │   │   │   ├── did.mcfunction
        │   │       │   │   │   ├── effect.mcfunction
        │   │       │   │   │   ├── effect_o.mcfunction
        │   │       │   │   │   └── test.mcfunction
        │   │       │   │   └── opium/
        │   │       │   │       ├── did.mcfunction
        │   │       │   │       ├── effect.mcfunction
        │   │       │   │       ├── effect_o.mcfunction
        │   │       │       └── test.mcfunction
        │   │       ├── replicater/
        │   │       │   ├── book.mcfunction
        │   │       │   ├── menu.mcfunction
        │   │       │   └── totem.mcfunction
        │   │       ├── team/
        │   │       │   ├── create_operate.mcfunction
        │   │       │   ├── create_team.mcfunction
        │   │       │   ├── function.mcfunction
        │   │       │   ├── manage.mcfunction
        │   │       │   ├── refuse.mcfunction
        │   │       │   ├── set.mcfunction
        │   │       │   ├── setting.mcfunction
        │   │       │   ├── be_invite/
        │   │       │   │   ├── agree.mcfunction
        │   │       │   │   ├── dialog.mcfunction
        │   │       │   │   ├── dialog_macro.mcfunction
        │   │       │   │   ├── dialog_macro2.mcfunction
        │   │       │   │   ├── operate.mcfunction
        │   │       │   │   ├── repulse.mcfunction
        │   │       │   │   ├── tellraw.mcfunction
        │   │       │   ├── glow/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── invite/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── leave/
        │   │       │   │   ├── debug.mcfunction
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   └── tellraw.mcfunction
        │   │       │   └── setting/
        │   │       │       ├── bex.mcfunction
        │   │       │       ├── color.mcfunction
        │   │       │       ├── empty.mcfunction
        │   │       │       ├── friendly_fire.mcfunction
        │   │       │       ├── glow.mcfunction
        │   │       │       ├── invite.mcfunction
        │   │       │       ├── prx.mcfunction
        │   │       │       ├── word.mcfunction
        │   │       │       ├── boolean/
        │   │       │       │   ├── friendly.mcfunction
        │   │       │       │   ├── glow.mcfunction
        │   │       │       │   └── invite.mcfunction
        │   │       │       ├── empty/
        │   │       │       │   ├── finish.mcfunction
        │   │       │       │   └── true.mcfunction
        │   │       │       ├── friendly/
        │   │       │       │   ├── false.mcfunction
        │   │       │       │   └── ture.mcfunction
        │   │       │       ├── glow/
        │   │       │       │   ├── false.mcfunction
        │   │       │       │   └── ture.mcfunction
        │   │       │       ├── invite/
        │   │       │       │   ├── false.mcfunction
        │   │       │       │   └── ture.mcfunction
        │   │       │       └── word/
        │   │       │           ├── error.mcfunction
        │   │       │           ├── bex/
        │   │       │           │   ├── dialog.mcfunction
        │   │       │           │   └── finish.mcfunction
        │   │       │           └── prx/
        │   │       │               ├── dialog.mcfunction
        │   │       │               └── finish.mcfunction
        │   │       ├── test/
        │   │       │   ├── did.mcfunction
        │   │       │   ├── did2.mcfunction
        │   │       │   └── summon.mcfunction
        │   │       ├── tool/
        │   │       │   ├── chopper/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── loop.mcfunction
        │   │       │   │   └── marker.mcfunction
        │   │       │   ├── dirt/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── face.mcfunction
        │   │       │   │   └── marker.mcfunction
        │   │       │   ├── oldchopper/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── loop.mcfunction
        │   │       │   │   ├── loop_j.mcfunction
        │   │       │   │   └── marker.mcfunction
        │   │       │   ├── tunnel/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── face.mcfunction
        │   │       │   │   └── marker.mcfunction
        │   │       │   └── veinmine/
        │   │       │       ├── did.mcfunction
        │   │       │       ├── loop.mcfunction
        │   │       │       └── marker.mcfunction
        │   │       ├── tpa/
        │   │       │   ├── accept.mcfunction
        │   │       │   ├── ask.mcfunction
        │   │       │   ├── be_accepted.mcfunction
        │   │       │   ├── be_asked.mcfunction
        │   │       │   ├── excute.mcfunction
        │   │       │   ├── list.mcfunction
        │   │       │   ├── list_loop.mcfunction
        │   │       │   ├── repulse.mcfunction
        │   │       │   ├── repulsed.mcfunction
        │   │       │   ├── request.mcfunction
        │   │       │   ├── times_out.mcfunction
        │   │       │   └── sorting/
        │   │       │       ├── dialog.mcfunction
        │   │       │       ├── did.mcfunction
        │   │       │       └── loop.mcfunction
        │   │       │       └── merge.mcfunction
        │   │       ├── tp_port/
        │   │       │   ├── pass.mcfunction
        │   │       │   ├── set.mcfunction
        │   │       │   ├── set_check.mcfunction
        │   │       │   └── tele/
        │   │       │       ├── d.mcfunction
        │   │       │       ├── did.mcfunction
        │   │       │       ├── test.mcfunction
        │   │       ├── useful/
        │   │       │   ├── did.mcfunction
        │   │       │   ├── put_head.mcfunction
        │   │       │   ├── infor/
        │   │       │   │   ├── day.mcfunction
        │   │       │   │   ├── time.mcfunction
        │   │       │   │   └── weather.mcfunction
        │   │       │   ├── seat/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── fall.mcfunction
        │   │       │   │   └── fall_check.mcfunction
        │   │       │   ├── show_item/
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── get_resolved_item_name.mcfunction
        │   │       │   │   ├── show.mcfunction
        │   │       │   │   └── who.mcfunction
        │   │       │   └── store/
        │   │       │       ├── fall_check.mcfunction
        │   │       │       ├── base/
        │   │       │       │   └── did.mcfunction
        │   │       │       └── head/
        │   │       │           ├── did.mcfunction
        │   │       │           └── summon.mcfunction
        │   │       ├── weapens/
        │   │       │   ├── did.mcfunction
        │   │       │   ├── dagger/
        │   │       │   │   └── did.mcfunction
        │   │       │   │   └── tell.mcfunction
        │   │       │   ├── handle/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── katana/
        │   │       │   │   ├── damage.mcfunction
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── fail.mcfunction
        │   │       │   │   ├── hp_test.mcfunction
        │   │       │   │   ├── no.mcfunction
        │   │       │   │   └── sword.mcfunction
        │   │       │   ├── rapier/
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── sickle/
        │   │       │   │   ├── damage.mcfunction
        │   │       │   │   └── did.mcfunction
        │   │       │   ├── sword/
        │   │       │   │   ├── damage.mcfunction
        │   │       │   │   ├── did.mcfunction
        │   │       │   │   ├── loop.mcfunction
        │   │       │   │   └── db/
        │   │       │   │       ├── did.mcfunction
        │   │       │   │       └── loop.mcfunction
        │   │       └── whip/
        │   │           └── did.mcfunction
        │   ├── item_modifier/
        │   │   ├── damage.json  # 伤害减少 - 将数量减少1
        │   │   └── minus.json  # 计数减少 - 物品计数-1
        │   ├── jukebox_song/
        │   │   └── mango.json  # 芒果醬——我喜歡你 - 111秒的自定义歌曲
        │   ├── loot_table/
        │   │   ├── id.json  # 玩家头颅掉落 - 玩家死亡掉落对应的头颅
        │   │   ├── muj.json  # MUJ掉落物 - 方块爆炸掉落处理
        │   │   └── adv/
        │   │       ├── death/
        │   │       │   ├── 2.json
        │   │       │   ├── 3.json
        │   │       │   ├── 4.json
        │   │       │   └── dog.json
        │   │       ├── entity/
        │   │       │   ├── ghast.json
        │   │       │   ├── kill_horse.json
        │   │       │   └── zhang.json
        │   │       ├── fight/
        │   │       │   ├── clown.json
        │   │       │   ├── clown_fish.json
        │   │       │   ├── god.json
        │   │       │   └── heavy.json
        │   │       ├── fish/
        │   │       │   ├── fish.json
        │   │       │   ├── fish_cook.json
        │   │       │   ├── fly_fish.json
        │   │       │   ├── fly_fish_pro.json
        │   │       │   ├── horn.json
        │   │       │   └── light.json
        │   │       ├── times/
        │   │       │   └── decade.json
        │   │       └── walk/
        │   │           ├── 1.json
        │   │           ├── 2.json
        │   │           ├── 3.json
        │   │           ├── 64.json
        │   │           ├── ccp.json
        │   │           ├── nonono.json
        │   │           └── smmw.json
        │   ├── predicate/
        │   │   ├── clean.json  # 晴朗天气 - 判断非雨非雷天
        │   │   ├── ghast.json  # 恶魂判断 - 恶魂检测谓词
        │   │   ├── hourse.json  # 马判断 - 马检测谓词
        │   │   ├── rain.json  # 下雨天气 - 判断下雨(非雷)
        │   │   ├── sneak.json  # 潜行状态 - 判断玩家是否潜行
        │   │   └── thundering.json  # 雷电天气 - 判断雷暴天气
        │   ├── recipe/
        │   │   ├── amethyst.json  # 紫水晶分解 - 将紫水晶块切割为4个碎片
        │   │   ├── amethyst_budding.json  # 紫水晶芽配方
        │   │   ├── menu.json  # 菜单替代物 - 纸质菜单合成
        │   │   ├── monster_spawner.json  # 怪物生成器 - 紫水晶、铁栏杆、钟、强化深板岩合成
        │   │   ├── test.json  # 测试配方
        │   │   ├── tetanus_book.json  # 破伤风书配方
        │   │   ├── build/
        │   │   │   ├── capurer.json
        │   │   │   ├── cb.json
        │   │   │   ├── forge.json
        │   │   │   ├── griner.json
        │   │   │   ├── replicater.json
        │   │   │   ├── rf.json
        │   │   │   ├── tp_port.json
        │   │   │   └── vault.json
        │   │   ├── hammer/
        │   │   │   ├── diamond_hammer.json
        │   │   │   ├── iron_hammer.json
        │   │   │   └── netherite_hammer.json
        │   │   ├── medical/
        │   │   │   ├── smoking_pipe.json
        │   │   │   └── syringe.json
        │   │   ├── metiral/
        │   │   │   ├── bronze_ingot.json
        │   │   │   ├── crude_oil_bucket.json
        │   │   │   ├── magic_dust.json
        │   │   │   ├── siron_ingot.json
        │   │   │   ├── steel_ingot.json
        │   │   │   └── uziron_ingot.json
        │   │   ├── tool/
        │   │   │   ├── chopper.json
        │   │   │   ├── entrencher.json
        │   │   │   ├── netherite_shears.json
        │   │   │   ├── paxel.json
        │   │   │   ├── tunneler.json
        │   │   │   └── word_destructer.json
        │   │   └── weapen/
        │   │       ├── fireball.json
        │   │       └── whip.json
        │   ├── structure/
        │   ├── tags/
        │   │   ├── block/
        │   │   │   ├── canplant.json
        │   │   │   ├── canthough.json
        │   │   │   ├── tunnel.json
        │   │   │   └── veinminable.json
        │   │   ├── entity_type/
        │   │   │   ├── bug.json
        │   │   │   ├── capurable.json
        │   │   │   ├── desert_undead.json
        │   │   │   ├── d_move.json
        │   │   │   ├── fightable.json
        │   │   │   ├── friendly.json
        │   │   │   ├── hourse.json
        │   │   │   ├── lowhp.json
        │   │   │   ├── skeleton.json
        │   │   │   ├── undead.json
        │   │   │   ├── undead_og.json
        │   │   │   └── zombie.json
        │   │   ├── fluid/
        │   │   ├── function/
        │   │   └── item/
        │   │       ├── bone.json
        │   │       ├── fish.json
        │   │       ├── fish_cook.json
        │   │       ├── forge_ingot.json
        │   │       ├── handle.json
        │   │       ├── medical_metiral.json
        │   │       ├── metiral.json
        │   │       ├── string.json
        │   │       ├── stripped.json
        │   │       └── enchantable/
        │   │           └── rustable.json
        │   ├── trim_material/
        │   ├── trim_pattern/
        │   └── worldgen/
        │       └── biome/
        ├── debug/
        │   └── function/
        │       ├── rescore.mcfunction
        │       ├── re_sum_cb.mcfunction
        │       ├── score.mcfunction
        │       └── data/
        │           └── re_sum_cb.mcfunction
        ├── minecraft/
        │   ├── enchantment/
        │   │   ├── aqua_affinity.json
        │   │   ├── bane_of_arthropods.json
        │   │   ├── binding_curse.json
        │   │   ├── blast_protection.json
        │   │   ├── breach.json
        │   │   ├── channeling.json
        │   │   ├── density.json
        │   │   ├── depth_strider.json
        │   │   ├── efficiency.json
        │   │   ├── feather_falling.json
        │   │   ├── fire_aspect.json
        │   │   ├── fire_protection.json
        │   │   ├── flame.json
        │   │   ├── fortune.json
        │   │   ├── frost_walker.json
        │   │   ├── impaling.json
        │   │   ├── infinity.json
        │   │   ├── knockback.json
        │   │   ├── looting.json
        │   │   ├── loyalty.json
        │   │   ├── luck_of_the_sea.json
        │   │   ├── lunge.json
        │   │   ├── lure.json
        │   │   ├── mending.json
        │   │   ├── multishot.json
        │   │   ├── piercing.json
        │   │   ├── power.json
        │   │   ├── projectile_protection.json
        │   │   ├── protection.json
        │   │   ├── punch.json
        │   │   ├── quick_charge.json
        │   │   ├── respiration.json
        │   │   ├── riptide.json
        │   │   ├── sharpness.json
        │   │   ├── silk_touch.json
        │   │   ├── smite.json
        │   │   ├── soul_speed.json
        │   │   ├── sweeping_edge.json
        │   │   ├── swift_sneak.json
        │   │   ├── thorns.json
        │   │   ├── unbreaking.json
        │   │   ├── vanishing_curse.json
        │   │   ├── wind_burst.json
        │   │   ├── projectile_protection.json
        │   │   ├── protection.json
        │   │   ├── punch.json
        │   │   ├── quick_charge.json
        │   │   ├── respiration.json
        │   │   ├── riptide.json
        │   │   ├── sharpness.json
        │   │   ├── silk_touch.json
        │   │   ├── smite.json
        │   │   ├── soul_speed.json
        │   │   ├── sweeping_edge.json
        │   │   ├── swift_sneak.json
        │   │   ├── thorns.json
        │   │   ├── unbreaking.json
        │   │   ├── vanishing_curse.json
        │   │   └── wind_burst.json
        │   ├── enchantment_provider/
        │   │   ├── enderman_loot_drop.json
        │   │   ├── mob_spawn_equipment.json
        │   │   ├── pillager_spawn_crossbow.json
        │   │   └── raid/
        │   │       ├── pillager_post_wave_3.json
        │   │       ├── pillager_post_wave_5.json
        │   │       ├── vindicator.json
        │   │       └── vindicator_post_wave_5.json
        │   ├── loot_table/
        │   │   ├── blocks/
        │   │   │   ├── bush.json
        │   │   │   └── reinforced_deepslate.json
        │   │   └── gameplay/
        │   │       └── sniffer_digging.json
        │   └── tags/
        │       ├── damage_type/
        │       │   ├── bypasses_armor.json
        │       │   ├── bypasses_cooldown.json
        │       │   ├── bypasses_effects.json
        │       │   ├── bypasses_enchantments.json
        │       │   ├── bypasses_resistance.json
        │       │   ├── bypasses_shield.json
        │       │   └── bypasses_invulnerability.json
        │       ├── dialog/
        │       │   └── quick_actions.json
        │       ├── enchantment/
        │       │   ├── curse.json
        │       │   ├── double_trade_price.json
        │       │   ├── in_enchanting_table.json
        │       │   ├── non_treasure.json
        │       │   ├── on_mob_spawn_equipment.json
        │       │   ├── on_random_loot.json
        │       │   ├── on_traded_equipment.json
        │       │   ├── prevents_bee_spawns_when_mining.json
        │       │   ├── prevents_decorated_pot_shattering.json
        │       │   ├── prevents_ice_melting.json
        │       │   └── prevents_bee_spawns_when_mining.json
        │       │   └── prevents_decorated_pot_shattering.json
        │       │   └── prevents_ice_melting.json
        │       └── function/
        │           ├── load.json
        │           └── tick.json
        └── summon/
            └── function/
                └── villager.mcfunction
```

## 檔案功能說明

以下是工作區中各檔案和目錄的功能描述，使用繁體中文說明。

### 根目錄檔案
- **README.md**: 專案的說明文件，包含專案概述、安裝說明和使用指南。

### build_height 數據包
- **pack.mcmeta**: 數據包的元數據檔案，定義數據包的版本和描述。
- **data/minecraft/dimension_type/**: 定義維度類型。
  - **overworld_caves.json**: 定義主世界洞穴維度的屬性，如高度限制。
  - **overworld.json**: 定義主世界維度的屬性，如高度限制。

### for308 數據包
- **pack.mcmeta**: 數據包的元數據檔案。
- **.vscode/settings.json**: VS Code 編輯器的設定檔案，用於配置編輯器行為。

#### data/308/ 命名空間
- **advancement/**: 定義玩家進度（成就）。
  - 各種進度檔案，如 chundo_man.json（進度：成為傳奇鐵匠大師）、exppp_god.json（進度：成為經驗之神）等。
- **damage_type/**: 定義自訂傷害類型。
  - **player_attack_ex.json**: 自訂玩家攻擊傷害類型。
- **dialog/**: 定義對話介面。
  - 各種對話檔案，如 exp_menu.json（經驗選單）、team.json（團隊管理）等。
- **enchantment/**: 自訂附魔。
  - **poison.json**: 毒藥附魔。
  - **tetanus.json**: 破傷風附魔。
  - **tool/**: 工具相關附魔。
- **function/**: 函數腳本，處理遊戲邏輯。
  - **adv.mcfunction**: 進度相關函數。
  - **load.mcfunction**: 數據包載入時執行的函數。
  - **tick.mcfunction**: 每遊戲刻執行的函數。
  - **build/**: 建築相關函數，如鐵砧操作、磨石機等。
  - **mob/**: 怪物相關函數，如召喚和行為。
  - **player/**: 玩家相關函數，如經驗管理、團隊系統、醫療系統等。
- **item_modifier/**: 物品修改器。
  - **damage.json**: 傷害修改。
  - **minus.json**: 減少數值修改。
- **jukebox_song/**: 自訂唱片歌曲。
  - **mango.json**: 芒果歌曲。
- **loot_table/**: 戰利品表。
  - **id.json**: ID 相關戰利品。
  - **muj.json**: 某種物品戰利品。
  - **adv/**: 進度相關戰利品。
- **predicate/**: 條件判斷。
  - 各種條件檔案，如 clean.json（清潔條件）、rain.json（下雨條件）等。
- **recipe/**: 配方定義。
  - 各種配方，如 amethyst.json（紫水晶配方）、hammer/（錘子配方）等。
- **tags/**: 標籤定義，用於分類物品、實體等。
  - **block/**: 方塊標籤。
  - **entity_type/**: 實體類型標籤。
  - **item/**: 物品標籤。
- **worldgen/biome/**: 世界生成生物群系。

#### data/debug/ 命名空間
- **function/**: 除錯相關函數。
  - **score.mcfunction**: 分數管理。
  - **rescore.mcfunction**: 重新計分。
  - **re_sum_cb.mcfunction**: 重新總結某項數據。

#### data/minecraft/ 命名空間
- **enchantment/**: Minecraft 原生附魔的覆蓋或擴展。
- **enchantment_provider/**: 附魔提供者。
- **loot_table/**: 原生戰利品表的修改。
- **tags/**: 原生標籤的修改。

#### data/summon/ 命名空間
- **function/villager.mcfunction**: 召喚村民的函數。