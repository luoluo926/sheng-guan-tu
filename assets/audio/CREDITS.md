# 音频素材来源与命名对照

本目录音频均来自用户提供的素材包，许可证见同目录 `LICENSE-free_sample_pack.txt`、`LICENSE-marutto-sfx.txt`（个人/商用可用，禁止二次分发素材本身）。

## 背景音乐（bgm/）

| 新文件名 | 原始文件 | 用途 |
| --- | --- | --- |
| `vermilion_corridor.mp3` | `C140B_Vermilion_Corridor.mp3` | 主菜单 / 选人 / 准备界面 |
| `lantern_alley.mp3` | `C175A_Lantern_Alley.mp3` | 正式对局 |

## 音效（sfx/）

| 新文件名 | 原始文件 | 来源包 | 游戏事件 |
| --- | --- | --- | --- |
| `click.mp3` | `ui_001_クリックA_click_a.mp3` | marutto | 按钮点击 |
| `select.mp3` | `ui_007_カーソル移動A_cursor_a.mp3` | marutto | 切换人物 / 选择目标 |
| `confirm.mp3` | `ui_013_決定音A_confirm_a.mp3` | marutto | 确定、落子、确认选择 |
| `cancel.mp3` | `ui_021_キャンセル音A_cancel_a.mp3` | marutto | 关闭弹窗 / 取消 |
| `toggle.mp3` | `ui_046_トグルONA_toggle_on_a.mp3` | marutto | 音频开关切换 |
| `paper_flip.mp3` | `dy_011_紙めくりA_paper_flip_a.mp3` | marutto | 抽牌、翻牌、查看牌义 |
| `paper_crumple.mp3` | `dy_015_紙くしゃくしゃA_paper_crumple_a.mp3` | marutto | 弃牌 |
| `book_close.mp3` | `dy_048_本を閉じるA_book_close_a.mp3` | marutto | 收起图鉴 / 牌库 |
| `coin.mp3` | `gm_019_コイン獲得A_coin_a.mp3` | marutto | 获得资望 / 打点 |
| `levelup.mp3` | `gm_031_レベルアップA_levelup_a.mp3` | marutto | 科举晋升、升阶 |
| `damage.mp3` | `gm_036_ダメージA_damage_a.mp3` | marutto | 降级、被参劾、革职 |
| `powerup.mp3` | `gm_025_パワーアップA_powerup_a.mp3` | marutto | 加官、花红、带级等增益 |
| `sparkle.mp3` | `mg_001_キラキラA_sparkle_a.mp3` | marutto | 金榜题名、及第光效 |
| `heal.mp3` | `mg_023_回復の光A_heal_a.mp3` | marutto | 辩白、抵消参劾 |
| `notify.mp3` | `nt_024_お知らせアルペジオA_notify_arp_a.mp3` | marutto | 回合切换、轮到你、恩科 |
| `transition.mp3` | `jg_015_場面転換A_transition_a.mp3` | marutto | 菜单 → 对局场景切换 |
| `taiko.mp3` | `wd_002_大太鼓B_taiko_b.mp3` | free_sample_pack | 参劾、清查等重手牌 |
| `temple_bell.mp3` | `wf_001_梵鐘A_temple_bell_a.mp3` | free_sample_pack | 殿试揭榜、胜利钟声 |
| `wind_chime.mp3` | `wn_001_風鈴A_wind_chime_a.mp3` | free_sample_pack | 资望小幅增加、任务提示 |
| `shoji_open.mp3` | `wh_001_障子を開けるA_shoji_open_a.mp3` | free_sample_pack | 打开弹窗 / 骰盘 |
| `shoji_close.mp3` | `wh_003_障子を閉めるA_shoji_close_a.mp3` | free_sample_pack | 关闭弹窗 / 骰盘 |

## 未采用素材

两个素材包中的拔刀、水滴、键盘、鼠标、小川环境音等与本作科举题材不符，未纳入项目；仅保留原始授权文件，不复制音频本体。

## 合成音效

陀螺旋转（1.5s 缓停）与棋盘逐格移动的轻木鱼点，素材包内无合适音源，由 Web Audio API 实时合成（噪声带通扫频 + 短促木击），不新增文件。
