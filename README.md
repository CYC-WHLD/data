# Minecraft 資料包結構說明 (中文註解版本)

基於編碼內容分析，此工作區包含兩個 Minecraft 資料包：`build_height` 和 `for308`。以下是詳細的資料夾結構說明，註解基於文件內容和 Minecraft 資料包標準結構。

## 整體結構

```
datapacks/
├── build_height/          # 建築高度資料包 - 修改世界高度限制至 448 格
│   ├── pack.mcmeta         # 資料包元數據 (格式版本 75)
│   └── data/
│       └── minecraft/      # Minecraft 官方命名空間
│           └── dimension_type/  # 維度類型定義
│               ├── overworld.json       # 主世界維度 - 高度: 448, 最低高度: -64
│               └── overworld_caves.json # 主世界洞穴維度 - 類似修改
│
└── for308/                # 308 班級資料包 - 學校競賽/遊戲系統
    ├── pack.mcmeta         # 資料包元數據 (格式版本 75)
    ├── .vscode/            # VS Code 編輯器設定
    │   └── settings.json   # 編輯器配置
    └── data/
        ├── 308/            # 自定義命名空間 "308" (代表班級)
        │   ├── advancement/     # 進度系統 - 競賽成就
        │   │   ├── start.json           # 起點進度 - "起點－－八班－－"
        │   │   ├── chundo.json          # 成都進度
        │   │   ├── chundo_man.json      # 成都大師
        │   │   ├── chundo_master.json   # 成都宗師
        │   │   ├── copper.json          # 銅相關進度
        │   │   ├── exppp.json           # 經驗擴展進度
        │   │   ├── exppp_master.json    # 經驗擴展大師
        │   │   ├── exppp_god.json       # 經驗擴展神級
        │   │   ├── lever.json           # 槓桿進度
        │   │   ├── repulse.json         # 反衝進度
        │   │   ├── death/               # 死亡相關進度子資料夾
        │   │   ├── entity/              # 實體相關進度
        │   │   ├── fight/               # 戰鬥進度
        │   │   ├── fish/                # 釣魚進度
        │   │   ├── forge/               # 鍛造進度
        │   │   ├── main/                # 主要進度
        │   │   ├── medical/             # 醫療進度
        │   │   ├── times/               # 時間相關進度
        │   │   ├── use/                 # 使用物品進度
        │   │   └── walk/                # 行走進度
        │   │
        │   ├── damage_type/     # 自定義傷害類型
        │   │   └── player_attack_ex.json  # 玩家攻擊額外傷害
        │   │
        │   ├── datapack/        # 資料包相關配置 (空)
        │   │
        │   ├── dialog/          # 對話系統 - 功能選單
        │   │   ├── exp_menu.json        # 經驗選單
        │   │   ├── give_bu.json         # 給予增益
        │   │   ├── olduseful.json       # 舊版實用功能
        │   │   ├── phiz.json            # 表情功能
        │   │   ├── team_set.json        # 隊伍設定
        │   │   ├── team.json            # 隊伍管理
        │   │   ├── test.json            # 測試對話
        │   │   ├── tpa.json             # 傳送請求
        │   │   ├── tpayesno.json        # 傳送確認
        │   │   ├── useful.json          # 實用功能
        │   │   └── exp/                 # 經驗相關對話子資料夾
        │   │
        │   ├── dimension/       # 自定義維度 (空)
        │   ├── dimension_type/  # 自定義維度類型 (空)
        │   │
        │   ├── enchantment/     # 自定義附魔
        │   │   ├── poison.json          # 毒附魔
        │   │   ├── tetanus.json         # 破傷風附魔
        │   │   └── tool/                # 工具附魔子資料夾
        │   │
        │   ├── enchantment_provider/  # 附魔提供者 (空)
        │   │
        │   ├── function/        # 函數腳本 - 遊戲邏輯
        │   │   ├── load.mcfunction      # 載入函數 - 初始化計分板和系統
        │   │   ├── tick.mcfunction      # 每 tick 執行函數
        │   │   ├── sec.mcfunction       # 每秒執行函數
        │   │   ├── adv.mcfunction       # 進度相關函數
        │   │   ├── build/               # 建築相關函數
        │   │   ├── mob/                 # 怪物相關函數
        │   │   └── player/              # 玩家相關函數
        │   │
        │   ├── item_modifier/   # 物品修改器
        │   │   ├── damage.json          # 傷害修改
        │   │   └── minus.json           # 減法修改
        │   │
        │   ├── jukebox_song/    # 唱片機歌曲
        │   │   └── mango.json           # 芒果歌曲
        │   │
        │   ├── loot_table/      # 戰利品表
        │   │   ├── id.json              # ID 相關戰利品
        │   │   ├── muj.json             # 未知戰利品
        │   │   └── adv/                 # 進度相關戰利品
        │   │
        │   ├── predicate/       # 謂詞條件
        │   │   ├── clean.json           # 清潔條件
        │   │   ├── ghast.json           # 幽靈條件
        │   │   ├── hourse.json          # 馬條件 (拼寫錯誤?)
        │   │   ├── rain.json            # 下雨條件
        │   │   ├── sneak.json           # 潛行條件
        │   │   └── thundering.json      # 雷雨條件
        │   │
        │   ├── recipe/          # 自定義配方
        │   │   ├── menu.json            # 菜單物品配方 (菜單替代物)
        │   │   ├── amethyst.json        # 紫水晶配方
        │   │   ├── amethyst_budding.json # 紫水晶芽配方
        │   │   ├── monster_spawner.json # 怪物生成器配方
        │   │   ├── test.json            # 測試配方
        │   │   ├── tetanus_book.json    # 破傷風書配方
        │   │   ├── build/               # 建築配方
        │   │   ├── hammer/              # 錘子配方
        │   │   ├── medical/             # 醫療配方
        │   │   ├── metiral/             # 材料配方 (拼寫錯誤?)
        │   │   ├── tool/                # 工具配方
        │   │   └── weapen/              # 武器配方 (拼寫錯誤?)
        │   │
        │   ├── structure/       # 結構 (空)
        │   │
        │   ├── tags/            # 標籤系統
        │   │   ├── block/               # 方塊標籤
        │   │   ├── entity_type/         # 實體類型標籤
        │   │   ├── fluid/               # 流體標籤
        │   │   ├── function/            # 函數標籤
        │   │   └── item/                # 物品標籤
        │   │
        │   ├── trim_material/   # 裝飾材料 (空)
        │   ├── trim_pattern/    # 裝飾圖案 (空)
        │   │
        │   └── worldgen/        # 世界生成
        │       └── biome/               # 生物群系
        │
        ├── debug/              # 除錯功能
        │   └── function/
        │       ├── score.mcfunction     # 計分函數
        │       ├── rescore.mcfunction   # 重置計分
        │       ├── re_sum_cb.mcfunction # 重置總結
        │       └── data/                # 資料子資料夾
        │
        ├── minecraft/          # Minecraft 命名空間覆蓋
        │   ├── enchantment/     # 覆蓋官方附魔
        │   │   ├── aqua_affinity.json   # 水下親和
        │   │   ├── bane_of_arthropods.json # 節肢剋星
        │   │   ├── binding_curse.json   # 綁定詛咒
        │   │   ├── blast_protection.json # 爆炸保護
        │   │   ├── breach.json          # 破裂
        │   │   ├── channeling.json      # 引雷
        │   │   ├── density.json         # 密度
        │   │   ├── depth_strider.json   # 深海行者
        │   │   ├── efficiency.json      # 效率
        │   │   ├── feather_falling.json # 輕盈
        │   │   ├── fire_aspect.json     # 火焰附加
        │   │   ├── fire_protection.json # 火焰保護
        │   │   ├── flame.json           # 火焰
        │   │   └── ... (更多附魔)
        │   │
        │   ├── enchantment_provider/  # 附魔提供者
        │   ├── loot_table/      # 戰利品表覆蓋
        │   └── tags/            # 標籤覆蓋
        │
        └── summon/             # 召喚系統
            └── function/       # 召喚函數
```

## 主要功能分析

### build_height 資料包
- **目的**: 修改 Minecraft 世界的建築高度限制
- **修改內容**: 
  - 世界高度從 384 增加到 448 格
  - 最低高度保持 -64
  - 適用於主世界和洞穴維度

### for308 資料包
- **目的**: 為 308 班級設計的競賽/遊戲系統資料包
- **主要功能**:
  - **計分板系統**: 追蹤玩家死亡、擊殺、移動距離等積分
  - **進度系統**: 多種成就，包括穿牆、經驗擴展、戰鬥等
  - **自定義附魔**: 毒、破傷風等特殊附魔
  - **配方系統**: 自定義物品製作，包括菜單物品、醫療物品等
  - **對話系統**: 功能選單、傳送、隊伍管理等
  - **函數系統**: 自動化遊戲邏輯，每 tick/秒執行

## 技術細節
- **Minecraft 版本**: 支援資料包格式 75 (約 1.21.x 版本)
- **命名空間**: `308` (自定義), `minecraft` (官方覆蓋)
- **程式語言**: Minecraft 函數語言 (.mcfunction)
- **配置格式**: JSON

此結構反映了一個完整的 Minecraft 資料包專案，包含競賽系統、建築修改和自定義內容。