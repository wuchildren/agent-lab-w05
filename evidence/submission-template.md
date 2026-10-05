# My lab evidence / 我的實作紀錄

- Group code / 組別：（自填）
- Tool / 工具：Claude（Cowork）代為執行，未使用 Codex
- Route / 路線：individual 個人，兩節路線
- Tasks completed / 完成題目：A、B（v1、v2）、D；Teachable Machine 兩類（red-circle、blue-square）
- Material / 素材：NDHU classroom tasks 東華課堂版
- My role and what I checked / 我的角色與實際檢查：A、B 的檔案、測試與 D 退回訊息由 Claude 完成；我負責建立 repo 後的 push、Teachable Machine 上傳與訓練，並看過結果。

## Scope and plan / 範圍與計畫

Allowed input and output folders / 可讀取與輸出的資料夾：
`practice/01-club-files`（input → output）、`practice/02-campus-picker`（activities.json → output/index.html）、`practice/04-review`。

What I asked for / 原始需求：照網站 A、B 任務卡整理 12 個社團檔案；做「課間我想做什麼？」單頁挑選器。

What I checked before execution / 動手前我檢查了什麼：只寫入 output、原檔不動、不刪檔、output 原本不存在、不連網不安裝。

## Tests actually performed / 我真的做過的測試

| Test / 測試 | Expected / 預期 | Observed / 實際 | Evidence / 證據 |
|---|---|---|---|
| 1 A：12 份副本 vs 原檔逐一比對 | 內容完全相同、12 檔都在 | 12/12 相同；manifest 12 筆 | commit「A: organize club files」 |
| 2 B：室外／15／中 | 顯示沒有符合的活動 | 顯示「沒有符合條件的活動」，未加入紀錄 | commit「B v1」 |
| 3 B：室內／15／低 抽 40 次 | 只出現 A01–A04 | 只出現 A01–A04 | 同上 |
| 4 B：不限／60／不限 抽 6 次 | 只留 5 筆，最新在前 | 5 筆，最新在前 | 同上 |

## One revision / 一次修改

Before / 原來的情況：看不出目前條件下有幾個活動可以抽。

Request / 我提出的修改：顯示「符合條件：N 個活動」，條件一改就更新。

After and retest / 修改後與重測結果：預設 9 個；室內／15／低＝4；室外／15／中＝0；切換英文顯示 Matching: N activities。原六組測試仍通過。

New requirement or defect? / 新需求還是原規格未做到？新需求，不是原本的錯誤。

## One rejection / 一次退回

Which action I reject and why / 退回哪個動作、為什麼：bad-plan.txt 要整理整個 Downloads、刪重複檔、把 final2 當最新版、自己補資料、自動公開。範圍太大、刪了救不回、會編造資料、沒經同意就公開。詳見 `practice/04-review/my-rejection.md`。

An acceptable alternative / 可以怎麼改：只動指定資料夾、不刪檔只標記、內容不同的版本都保留、缺資料標「待確認」、公開前先問我。

## Still unverified / 還沒驗證

What I cannot claim is complete / 哪些事不能說已完成：
- B 只在電腦瀏覽器測過，沒在真的手機上測。
- 六次測試不能證明隨機抽選的機率公平。
- Teachable Machine 測試：red-circle-test-1（變小、偏橘、紫色雜訊背景）被判成 blue-square 63%、red-circle 37%，**判錯了**（見 tm-test.png）。推測是每類只有 12 張、沒看過這種背景；改法是補上 13–24 張再訓練，這次還沒重測。
