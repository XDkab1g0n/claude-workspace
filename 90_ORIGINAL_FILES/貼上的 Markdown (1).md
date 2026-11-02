**我會選擇「Elf＋大雙子＋No.65＋Carrot，I\:P／紅淚／Sequence 留墓」作為主方案。**

它能保證自己回合抽一張，並在對手提供相應發動時點、場面未被拆掉的情況下，接出 **六次不同的 interaction，再抽一張**。關鍵是：**No.65 用完後成為 I\:P 的素材；W\:P 用其他怪獸做 S\:P，自己留下來使用無效。**

以下是依你提供的卡池、Konami 卡文與規則進行的紙上模擬，沒有在 MD 客戶端實跑。我比較了數條主要分支，但不把人工搜尋稱為已證明的全域最優。

四張原始手牌全程封存；本線要招募的卡視為仍在牌組。抽出的未知牌記為 **d**，保留在手，不假定抽到特定補點。

先統一簡稱：

| 簡稱卡片     |                               |
| -------- | ----------------------------- |
| 小紅       | Live☆Twin Ki-sikil            |
| 大紅       | Evil★Twin Ki-sikil            |
| 大藍       | Evil★Twin Lil-la              |
| 紅淚       | Lacrima the Crimson Tears     |
| 刻魔       | Fiendsmith Engraver           |
| 融合淚      | Fiendsmith's Lacrima          |
| 巨大       | Gigantic Spright              |
| Req／Seq  | Fiendsmith's Requiem／Sequence |
| IP／SP／WP | I\:P／S\:P／W\:P                |

**先確認這條線賴以成立的規則。**

- 小紅能從牌組叫任何符合名稱的「Lil-la」怪獸，因此可以叫 **Treat**。選它能多留下墓地戰鬥效果；換成通常小藍也能走同一主線。[小紅卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=15624\&ope=2)、[Treat 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=15719\&ope=2)
- Sweet 自蘇的惡魔族限制，只在該次自蘇的 Sweet 表側存在於怪獸區時適用；\*\*仍受限制時，不能直接拿她去做非惡魔族，企圖以離場解除限制。\*\*本線先用她做惡魔族 Seq。[Sweet 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=21165\&ope=2\&request_locale=en)
- Seq 的素材是「包含光屬性惡魔族的兩隻怪獸」，因此 **紅淚＋Sweet 合法**。[Seq 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20226\&ope=2\&request_locale=en)
- 巨大的效果處理後，雙方本回合只能特召等級／階級／Link 2；大雙子的復活效果則另外施加本回合額外牌組惡魔族限制。兩者會疊加，不能跨軸後忽略。[巨大卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=17449\&ope=2\&request_locale=en)、[大紅卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=15626\&ope=2)
- Elf 在對手控制怪獸時，可以復活墓地的 Link 2。因此，**已正規 Link 召喚、之後拿去當素材的 IP，可以在對手回合被 Elf 拉回。**[Elf 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=17451\&ope=2)

下面將記錄拆成同步台帳：每步場／墓／手、Extra 去向，以及效果次數與持續限制。**第 n 步的已用效果，包含所有使用步數 ≤ n 的紀錄；卡片離場不清零。**

---

自己回合的完整展開如下。表內手牌只列「可用手牌」；完整手牌始終另加四張封存牌。`〔〕` 表示 Xyz 素材，不計入場上怪獸或墓地。

| 步動作處理後場上處理後墓地可用手牌 |                                            |                                     |                                                 |         |
| ----------------- | ------------------------------------------ | ----------------------------------- | ----------------------------------------------- | ------- |
| 0                 | 起始                                         | —                                   | —                                               | 小紅      |
| 1                 | 通召小紅，效果從牌組特召 **Treat**                     | 小紅、Treat                            | —                                               | —       |
| 2                 | 小紅 → Link **Deal**                         | Treat、Deal                          | 小紅                                              | —       |
| 3                 | Deal 發動，將牌組 **Sweet** 送墓作 cost             | Treat、Deal                          | 小紅、Sweet                                        | —       |
| 4                 | 場上有 Deal，Sweet 發動自身效果復活                    | Treat、Deal、Sweet                    | 小紅                                              | —       |
| 5                 | Deal → Link **Req**                        | Treat、Sweet、Req                     | 小紅、Deal                                         | —       |
| 6                 | Req 解放自己，從牌組特召 **紅淚**                      | Treat、Sweet、紅淚                      | 小紅、Deal、Req                                     | —       |
| 7                 | 紅淚效果，將牌組 **刻魔** 送墓                         | Treat、Sweet、紅淚                      | 小紅、Deal、Req、刻魔                                  | —       |
| 8                 | **紅淚＋Sweet → Seq**；Sweet 的留場限制解除           | Treat、Seq                           | 小紅、Deal、Req、刻魔、紅淚、Sweet                         | —       |
| 9                 | Seq 將墓地 **Deal＋Req** 洗回 Extra，融合召喚 **融合淚** | Treat、Seq、融合淚                       | 小紅、刻魔、紅淚、Sweet                                  | —       |
| 10                | 融合淚效果，將墓地 **刻魔加入手牌**                       | Treat、Seq、融合淚                       | 小紅、紅淚、Sweet                                     | 刻魔      |
| 11                | 捨棄刻魔，檢索 **Tract**                          | Treat、Seq、融合淚                       | 小紅、紅淚、Sweet、刻魔                                  | Tract   |
| 12                | 發動 Tract，檢索 **Lurrie**，接著捨棄剛檢索的 Lurrie     | Treat、Seq、融合淚                       | 小紅、紅淚、Sweet、刻魔、Tract、Lurrie                     | —       |
| 13                | Lurrie 的誘發效果將自己特殊召喚                        | Treat、Seq、融合淚、Lurrie                | 小紅、紅淚、Sweet、刻魔、Tract                            | —       |
| 14                | **融合淚＋Lurrie → IP**                        | Treat、Seq、IP                        | 小紅、紅淚、Sweet、刻魔、Tract、融合淚、Lurrie                 | —       |
| 15                | 融合淚墓地效果，將 **Lurrie** 洗回牌組，造成 **1200 傷害**   | Treat、Seq、IP                        | 小紅、紅淚、Sweet、刻魔、Tract、融合淚                        | —       |
| 16                | 刻魔墓地效果，將 **融合淚** 洗回 Extra 作 cost，復活刻魔      | Treat、Seq、IP、刻魔                     | 小紅、紅淚、Sweet、Tract                               | —       |
| 17                | **Seq＋Treat → 巨大**；Seq 可依巨大自身規則當作等級 2 素材   | IP、刻魔、巨大〔Seq、Treat〕                 | 小紅、紅淚、Sweet、Tract                               | —       |
| 18                | 巨大效果，處理時卸除 **Seq**，從牌組特召 **Blue**          | IP、刻魔、巨大〔Treat〕、Blue                | 小紅、紅淚、Sweet、Tract、Seq                           | —       |
| 19                | Blue 檢索 **Jet**                            | IP、刻魔、巨大〔Treat〕、Blue                | 小紅、紅淚、Sweet、Tract、Seq                           | Jet     |
| 20                | 依 Jet 自身召喚方式特殊召喚 Jet                       | IP、刻魔、巨大〔Treat〕、Blue、Jet            | 小紅、紅淚、Sweet、Tract、Seq                           | —       |
| 21                | Jet 檢索 **Starter**                         | IP、刻魔、巨大〔Treat〕、Blue、Jet            | 小紅、紅淚、Sweet、Tract、Seq                           | Starter |
| 22                | **巨大＋刻魔 → Elf**；巨大剩餘素材 Treat 隨之送墓          | IP、Blue、Jet、Elf                     | 小紅、紅淚、Sweet、Tract、Seq、刻魔、巨大、Treat               | Starter |
| 23                | Elf 效果復活 **小紅**；場上有其他怪獸，小紅不能再招募            | IP、Blue、Jet、Elf、小紅                  | 紅淚、Sweet、Tract、Seq、刻魔、巨大、Treat                  | Starter |
| 24                | Starter 從牌組特召 **Carrot**，失去 **1000 LP**    | IP、Blue、Jet、Elf、小紅、Carrot           | 紅淚、Sweet、Tract、Seq、刻魔、巨大、Treat、Starter          | —       |
| 25                | **Blue＋Jet → No.65**                       | IP、Elf、小紅、Carrot、No.65〔Blue、Jet〕    | 紅淚、Sweet、Tract、Seq、刻魔、巨大、Treat、Starter          | —       |
| 26                | **IP＋小紅 → 大紅**；IP 在這次 Link 計為 1            | Elf、Carrot、No.65〔Blue、Jet〕、大紅       | 紅淚、Sweet、Tract、Seq、刻魔、巨大、Treat、Starter、IP、小紅    | —       |
| 27                | 場上沒有 Lil-la，大紅效果復活 **Sweet**               | Elf、Carrot、No.65〔Blue、Jet〕、大紅、Sweet | 紅淚、Tract、Seq、刻魔、巨大、Treat、Starter、IP、小紅          | —       |
| 28                | **大紅＋Sweet → 大藍**；大紅計為 1                   | Elf、Carrot、No.65〔Blue、Jet〕、大藍       | 紅淚、Tract、Seq、刻魔、巨大、Treat、Starter、IP、小紅、大紅、Sweet | —       |
| 29                | 場上沒有 Ki-sikil，大藍效果復活 **大紅**                | Elf、Carrot、No.65〔Blue、Jet〕、大藍、大紅    | 紅淚、Tract、Seq、刻魔、巨大、Treat、Starter、IP、小紅、Sweet    | —       |
| 30                | 大紅特殊召喚時有大藍，發動效果抽 **d**                     | 同上                                  | 同上                                              | d       |

幾個容易出錯的地方，對照實際卡文說明：

- \*\*第 9–16 步沒有動用封存手牌。\*\*融合淚能選擇把光惡魔加入手牌；Tract 捨棄的是自己剛搜尋的 Lurrie；融合淚與刻魔各自回收不同的光惡魔，沒有重複使用已離開墓地的卡。[融合淚](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20214\&ope=2\&request_locale=ae)、[刻魔](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20196\&ope=2\&request_locale=en)、[Tract](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20240\&ope=2\&request_locale=en)、[Lurrie](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=8092\&ope=2\&request_locale=en)
- \*\*IP 的初次召喚素材合法。\*\*融合淚是融合怪獸，Lurrie 是效果怪獸，兩者都不是 Link。[IP 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=14676\&ope=2)
- 第 25 步 Blue、Jet 都是闇屬性等級 2，符合 No.65 的指定素材。[Blue／Jet 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=17405\&ope=2)、[No.65 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=10778\&ope=2\&request_locale=en)
- 第 26 步大紅登場時沒有 Lil-la，**不抽牌**。第 28 步大藍登場時沒有 Ki-sikil，**不發動破壞**。真正的抽牌只有第 30 步。[大紅](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=15626\&ope=2)、[大藍](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=15627\&ope=2)

位置也能完整排開。將主怪獸區由左至右記為 M1–M5，使用左側 Extra Monster Zone：

| 階段位置安排    |                                        |
| --------- | -------------------------------------- |
| 前段        | Deal、Req、Seq 依序位於左側 EMZ；Treat 放 M5     |
| 第 14 步    | IP 放 Seq 指向的 M1                        |
| 第 17 步    | 巨大放 M5，釋放 EMZ                          |
| 第 20–21 步 | IP M1、刻魔 M2、Blue M3、Jet M4、巨大 M5       |
| 第 22–24 步 | Elf 放 EMZ；小紅復活到 M2；Carrot 放 M5         |
| 第 25 步    | No.65 放 M4                             |
| 第 26–28 步 | 大紅、大藍依序 Link 到 Elf 指向的 M1；Sweet 復活到 M2 |
| 第 29 步    | 大紅復活到 M2                               |

融合與 Xyz 可以直接召喚到主怪獸區；Link 召喚仍遵守 EMZ／箭頭要求。[官方規則更新](https://www.yugioh-card.com/en/play/2021_rules_update/)

Extra 的完整去向如下；沒有把同一張墓地卡再次當成 Extra 內的卡使用：

| Extra 卡首次使用後續去向 |    |                  |
| --------------- | -- | ---------------- |
| Deal            | 2  | 5 入墓；9 回 Extra   |
| Req             | 5  | 6 入墓；9 回 Extra   |
| Seq             | 8  | 17 成巨大素材；18 卸除入墓 |
| 融合淚             | 9  | 14 入墓；16 回 Extra |
| IP              | 14 | 26 入墓            |
| 巨大              | 17 | 22 入墓；Treat 同時送墓 |
| Elf①            | 22 | 留場               |
| No.65           | 25 | 留場，素材 Blue＋Jet   |
| 大紅              | 26 | 28 入墓；29 復活      |
| 大藍              | 28 | 留場               |

已用效果與召喚次數的累計台帳：

| 卡片使用紀錄  |                          |
| ------- | ------------------------ |
| 小紅      | 招募效果：1；通常召喚額度也在此使用       |
| Deal    | 本回合唯一一次 Link 召喚：2；堆墓效果：3 |
| Sweet   | 自身墓地復活：4                 |
| Req     | 本回合唯一一次特殊召喚：5；解放招募：6     |
| 紅淚      | 登場堆墓：7                   |
| Seq     | 融合效果：9                   |
| 融合淚     | 融合登場回收：10；送墓傷害：15        |
| 刻魔      | 捨棄檢索：11；墓地自蘇：16          |
| Tract   | 檢索／捨棄效果：12               |
| Lurrie  | 捨棄誘發復活：13；這不是一回合一次效果     |
| 巨大      | 招募效果：18                  |
| Blue    | 特召檢索：19；未使用自身手牌特召方式      |
| Jet     | 自身手牌特召：20；檢索：21          |
| Elf     | 復活：23                    |
| Starter | 卡片發動：24                  |
| 大紅      | 復活：27；抽牌：30              |
| 大藍      | 復活：29；破壞效果尚未使用           |

Req 的解放招募本身不是另寫一次限制的效果，但受到「Req 一回合只能特殊召喚一次」約束；本線只召喚一次。[Req 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20225\&ope=2\&request_locale=en)

**所有持續條件按下表累加，而非彼此取代：**

| 生效步數持續條件 |                                       |
| -------- | ------------------------------------- |
| 3 至回合結束  | Deal 的回應抽牌條件；本題對手不干擾，因此收益為 0          |
| 4–7      | Sweet 自蘇後表側留場：Extra 只能特召惡魔族           |
| 8 起      | Sweet 已作為 Seq 素材離場，上述限制解除             |
| 18 至回合結束 | 巨大：雙方只能特召等級／階級／Link 2                 |
| 22 至回合結束 | 本回合 Link 召喚的 Elf 不能作 Link 素材          |
| 24 至回合結束 | Starter 另外限制自己只能特召等級／階級／Link 2        |
| 26–27    | 當時的大紅取得 IP 給予的對手效果破壞抗性                |
| 27 至回合結束 | 大紅復活效果施加 Extra 惡魔族限制；第 29 步大藍再次施加相同限制 |
| 28 起     | 大紅離場，IP 給予它的抗性消失；29 復活後不保留            |

所以，第 27 步之後本回合的額外特召，必須**同時符合惡魔族與「2」限制**；本線後面只召喚大藍、復活大紅，合法。IP 抗性離場即消失，也有官方補充明文支持。[Starter](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=17457\&ope=2)、[Deal](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=21189\&ope=2\&request_locale=en)、[IP 官方補充](https://www.db.yugioh-card.com/yugiohdb/faq_search.action?cid=14676\&ope=4\&request_locale=ja)

---

自己回合結束時：

| 區域完整狀態   |                                                   |
| -------- | ------------------------------------------------- |
| 左側 EMZ   | **Elf①**                                          |
| M1       | **大藍**                                            |
| M2       | **大紅**                                            |
| M3       | 空                                                 |
| M4       | **No.65〔Blue、Jet〕**                               |
| M5       | **Carrot**                                        |
| 魔陷區      | 空                                                 |
| 手牌       | 四張封存牌＋d，共 **5 張**                                 |
| 墓地       | **小紅、Sweet、紅淚、刻魔、Tract、Treat、Starter、IP、Seq、巨大**  |
| 除外       | 無                                                 |
| 剩餘 Extra | **Deal、Req、融合淚、Desirae、Trouble Sunny、Elf②、SP、WP** |
| LP       | 自己 **7000**；對手 **6800**                           |

主牌組剩 **25 張**。五隻場上怪獸、兩張 Xyz 素材、十張墓地、五張手牌、二十五張主牌組、八張 Extra，合計仍為 **55 張**。

Elf 此時保護 M1 的大藍；空出的 M3 可在對手回合放復活的 IP。

資源收益是：

- 自己回合確定抽 **1 張**。
- 原始小紅從手牌投入後，以 d 補回，手牌總數回到五張。
- **紅淚＋Seq** 留墓，提供對手回合的額外素材。
- **IP 已正規召喚並留墓**，可以由 Elf 復活。
- Tract 的墓地融合效果尚未使用，可留待後續回合。
- Treat 留有戰鬥傷害後的降攻效果；它不計入下述主要六次 interaction。
- 第二張 Elf 尚未使用。它提供重建能力，**不會讓同一回合多用一次同名復活效果**。

---

**對手回合確實可以接出的六次 interaction，必須用一條共同合法的順序證明。**

以下示範要求對手先有怪獸留場，並陸續提供適合的怪獸效果、場上目標、魔陷發動時點。它不是「無論對手怎麼打都固定六擋」。

回合交替後，自己的巨大、Starter、大雙子等本回合限制均已結束；效果次數重新計算。

為縮短對手回合墓地台帳，從 O1 卸除素材後開始，固定墓地集合記為：

**B＝小紅、Sweet、刻魔、Tract、Treat、Starter、巨大、Blue、Jet。**

下表墓地欄均包含 B；每列新增的效果使用，持續累計到本回合結束。

| 步動作與新增效果使用處理後場上墓地中 B 以外的卡 |                                                       |                           |                 |
| ------------------------- | ----------------------------------------------------- | ------------------------- | --------------- |
| O1                        | 對手發動怪獸效果；No.65 卸除 Blue＋Jet，**無效發動，造成 500 傷害**         | Elf、大紅、大藍、Carrot、No.65〔空〕 | 紅淚、IP、Seq       |
| O2                        | 對手控制怪獸，Elf 復活 **IP 到 M3**                             | Elf、大紅、大藍、Carrot、No.65、IP | 紅淚、Seq          |
| O3                        | IP 效果：**IP〔計2〕＋空 No.65〔計1〕→ WP**，放 M3                 | Elf、大紅、大藍、Carrot、WP       | 紅淚、Seq、IP、No.65 |
| O4                        | 紅淚墓地效果，將自己洗回牌組，復活 **Seq 到 M4**                        | Elf、大紅、大藍、Carrot、WP、Seq   | IP、No.65        |
| O5                        | WP 加速 Link：**Seq〔計1〕＋大藍〔計1〕→ SP**，放 M1；**WP 留場**      | Elf、大紅、Carrot、WP、SP       | IP、No.65、Seq、大藍 |
| O6                        | SP 的 Link 召喚誘發效果，**除外場上或墓地一張卡**                       | 同上                        | 同上              |
| O7                        | 場上沒有 Lil-la，大紅效果復活 **大藍到 M4**                         | Elf、大紅、大藍、Carrot、WP、SP    | IP、No.65、Seq    |
| O8                        | 大藍特殊召喚時有大紅，**指定破壞一張場上卡**                              | 同上                        | 同上              |
| O9                        | 對手發動魔陷卡或效果；Carrot **解放大紅**，無效效果。因解放 Link 2，可再破壞該卡     | Elf、大藍、Carrot、WP、SP       | IP、No.65、Seq、大紅 |
| O10                       | 場上沒有 Ki-sikil，大藍效果復活 **大紅到 M2**                       | Elf、大紅、大藍、Carrot、WP、SP    | IP、No.65、Seq    |
| O11                       | 大紅特殊召喚時有大藍，**抽一張 d₂**                                 | 同上                        | 同上              |
| O12                       | 對手另一次場上／墓地怪獸效果發動；WP 暫時除外自己，**無效效果並除外該怪獸**             | Elf、大紅、大藍、Carrot、SP；WP 暫除 | 同上              |
| O13                       | 對手另一次卡片／效果發動；SP 指定**已用過效果的 Carrot＋對手一隻表側怪獸**，兩者暫除至 EP | Elf、大紅、大藍、SP；WP、Carrot 暫除 | 同上              |
| O14                       | EP：WP、Carrot 返回；原位置均保留空位                              | Elf、大紅、大藍、Carrot、WP、SP    | 同上              |

這條對手回合線的關鍵核對：

1. \*\*紅淚能拉 Seq。\*\*Seq 已在自己回合正規 Link 召喚，且 O4 時確實在墓地；紅淚返回牌組與復活 Seq 是其效果處理。[紅淚卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20490\&ope=2\&request_locale=en)
2. \*\*WP 不必參與自己的加速 Link。\*\*O5 使用的是 Seq＋大藍；因此 WP 保留下來，O12 還能使用另一個效果。這條路沒有使用對手怪獸作素材；只有 WP 自己參與素材時，才有使用對手 Link 2 以下怪獸的選項。[WP 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=22715\&ope=2\&request_locale=ja)
3. **SP 符合兩個效果怪獸的素材條件**，且使用了 Link 怪獸，能發動登場除外。兩隻 Link 2 各計為 1，合計 Link 2。[SP 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=19188\&ope=2\&request_locale=en)
4. \*\*O7 才重新吃到大雙子的惡魔族限制。\*\*IP、WP、SP 都已在此前完成特殊召喚。O7 之後使用 SP／WP 的效果沒有問題，因為限制的是額外特殊召喚，不是它們的效果發動。
5. \*\*Carrot 的 cost 不會永久損失大紅。\*\*O9 解放後，O10 用大藍拉回，再取得抽牌。大紅／大藍各自的復活、抽牌／破壞，均只使用一次。[Carrot 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=17405\&ope=2)
6. O6 起有 SP 的本回合不能直接攻擊條件；O7 起有 Extra 惡魔族限制。O12–O14 的暂除與返回沒有新增額外召喚。WP 使用自己無效效果後離場，**返回時不再保有 IP 給予的破壞抗性**；SP 從未取得這份抗性。[IP 官方補充](https://www.db.yugioh-card.com/yugiohdb/faq_search.action?cid=14676\&ope=4\&request_locale=ja)

因此，這條共同成立的順序提供的是：

| Interaction性質 |                            |
| ------------- | -------------------------- |
| No.65         | 一次怪獸效果**發動無效**；不附帶破壞       |
| SP 登場         | 一張場／墓卡除外                   |
| 大藍            | 一張場上卡指定破壞                  |
| Carrot        | 一次魔陷效果無效，並可破壞              |
| WP            | 一次場上／墓地怪獸效果無效並除外           |
| SP 快速效果       | 一隻對手怪獸暫時除外，搭配自己已用過的 Carrot |

**六次 interaction，不是六次無效，也不是六次永久除去。**

此外再抽 d₂，完整手牌變成 **四張封存牌＋d＋d₂**。若依表走完且沒有額外損失，對手 EP 後仍有 Elf、大雙子、Carrot、WP、SP 六隻怪獸。

順序上必須特別保留三件事：

- **Elf 拉 IP 之前，需要對手控制怪獸。**
- **WP 的加速 Link 要在大雙子的復活自肅之前完成。**
- \*\*WP 要先完成加速 Link，才把自己除外去無效。\*\*不能先消失，再把同一隻 WP 的加速 Link 算進來。

若對手很早就逼出 Carrot，或先處理 Elf，必須改線，不能繼續照表聲稱全部收益。WP 也不能在對手效果已發動後，才由 IP 召喚出來「補接」那次效果；它要預先登場。

---

我比較過的主要分支，以及為何採用這條：

| 分支可以取得的結果我的判斷         |                                                   |                                                            |
| --------------------- | ------------------------------------------------- | ---------------------------------------------------------- |
| **本案 No.65，IP 留墓**    | Elf＋大雙子＋No.65＋Carrot；自己抽一張；對手回合可接上述六次 interaction | 我優先採用；充分利用 Elf 復活 IP，以及空 No.65 的素材價值                       |
| **IP 留場、Jet 留場**      | Elf＋IP＋大雙子＋Jet＋Carrot，共六體                         | 合法，且不必等對手有怪獸才取得 IP；但在上述可完整運轉的情境，比主線少 No.65 那次無效            |
| **直接做 Desirae**       | Elf＋大雙子＋Carrot＋裝備 Seq 的 Desirae，自己抽一張             | 是有競爭力的替代方案；提供較直接、不取對象的表側卡無效                                |
| **Starter 改叫 Red**    | 同一主線，Carrot 換 Red                                 | 對大量怪獸效果的對局可選；未知對手時，我偏向保留魔陷應對                               |
| **Starter 叫 Blue②**   | 多一隻 Blue 身體                                       | Blue 檢索已在本回合用過，不能再搜一次；此處直接叫 Carrot／Red 更有即時價值              |
| **省略 Tract／Lurrie**   | 能到同樣的 No.65 終場                                    | 操作較短；少 1200 傷害，也沒有預先落墓的 Tract                              |
| **先做 Elf，再把 Elf 疊巨大** | 可以繼續展開，但需要考慮第二 Elf 重建                             | 會消耗額外身體與第二張 Elf；本線用 Seq＋Treat 疊巨大更節省                       |
| **Sunny 路線**          | 放棄或重新安排雷精軸，可走不同終場                                 | 巨大／Starter 已解決後不能再出 Link 4 Sunny；不能拿 Sunny 替換本線最後的大雙子而不付代價 |

其中，**Desirae 分支確實能保留雙子，不必把它做成孤立的刻魔終場**：

- 共用主線第 1–8 步。
- Seq 改把墓地 **刻魔＋Deal＋Req** 洗回，直接融合 Desirae。
- **Seq＋Treat → 巨大**，卸 Seq 拉 Blue，搜 Jet，再搜 Starter。
- **巨大＋Blue → Elf**；Elf 拉小紅，Starter 拉 Carrot。
- **小紅＋Jet → 大紅**，拉 Sweet；大紅＋Sweet 做大藍，大藍拉大紅抽一張。
- 墓地 Seq 裝備給 Desirae。

結果是 **Elf＋大雙子＋Carrot＋Desirae〔裝備 Seq〕**。Desirae 能一次無效最多兩張表側卡，但那是**一次效果處理**，不是可拆開使用的兩次康；送墓效果另有後續除去價值。[Desirae 卡文](https://www.db.yugioh-card.com/yugiohdb/card_search.action?cid=20215\&ope=2\&request_locale=en)

省略 Tract 的短線則是在第 9 步後：

**融合淚直接復活刻魔 → 融合淚＋刻魔做 IP → 刻魔洗回融合淚自蘇。**

便能回到主線第 16 步相同的場面與關鍵墓地，接著照走。完整線多出的 Tract／Lurrie 處理，沒有使用額外起手牌。

我的選擇是：\*\*未知對手、重視完整運轉後的干擾數量與資源循環時，採用 No.65／IP 留墓主線。\*\*它比單看五隻終場怪獸更強，因為 No.65、IP、紅淚、Seq 會依序轉成下一段資源。若更重視不依賴 Elf 復活 IP 的即時應對，或已知對局特別適合 Desirae，另外兩條就有各自的取捨；我沒有證據把其中任何一條宣稱為所有對局都嚴格最優。