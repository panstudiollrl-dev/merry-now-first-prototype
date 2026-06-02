# Merry Hearing Now-first UX 版本演進整理

更新日期：2026-06-02

可直接給 Claude / 設計協作者閱讀的版本脈絡文件。

Prototype 入口：

- 版本入口頁：https://panstudiollrl-dev.github.io/merry-now-first-prototype/
- v1：https://panstudiollrl-dev.github.io/merry-now-first-prototype/v1.html
- v2：https://panstudiollrl-dev.github.io/merry-now-first-prototype/v2.html

---

## 1. 產品定位

Merry Hearing 目前不應該被設計成「助聽器控制台」或「工程設定頁」。

我們目前的核心方向是：

> 一個讓使用者在「現在聽覺出了問題」時，可以立刻獲得協助的低干擾陪伴式介面。

使用者打開 app 的常見情境不是「想研究功能」，而是：

- 聽不清楚
- 其中一耳連不上
- 聲音刺耳、有雜音或不舒服
- 需要真人或聽檢師協助
- 不確定現在的環境要怎麼調整才安全

所以第一層介面應該降低焦慮、降低判斷負擔，而不是讓使用者進入複雜功能分類或技術名詞。

---

## 2. 到目前為止的核心設計原則

### 2.1 Problem-first，不是 Feature-first

首頁應該從使用者感受到的問題出發：

- I can’t hear clearly
- Won’t connect
- Noise or hiss
- Ask someone

而不是從功能名稱出發，例如：

- Sound Compass
- directional microphone
- acoustic analysis
- hearing profile
- device tuning

使用者打開 app 時通常不是想操作功能，而是想解決當下的困擾。

### 2.2 低干擾，但要讓人感覺被支援

Merry 應該像一個安靜但可靠的陪伴者。

好的 Merry 行為：

- 只在有意義時提示
- 用 icon 先讓使用者知道大意
- 用短句說明下一步
- 做完後給明確回饋
- 讓使用者知道「我現在被照顧到了」

不好的 Merry 行為：

- 一直跳提示
- 用太多文字
- 把每個狀態都做得像警報
- 把不能點的資訊做成按鈕
- 強迫使用者一開始填很多資料

### 2.3 Icon first，文字輔助

我們不應該假設使用者願意讀長文字。

許多提示最好是：

> 圖示 + 短標題 + 一句結果 / 下一步

例如：

- 右耳圖示 + Right aid seems weak
- 車流圖示 + Busy street detected
- 人聲圖示 + Speech is nearby

文字仍然需要，但應該短、清楚、靠近操作區。

### 2.4 穩定的首頁結構

即使未來加入個人化推薦，也不能讓首頁一直變動，讓使用者覺得「我怎麼不知道現在在哪裡」。

首頁應保留穩定骨架：

- 裝置與電量狀態
- 舒適音量控制
- 四張主要問題卡
- Merry noticed / 動態提示
- 場域聲音提示
- Care / 真人協助入口

推薦可以被凸顯，但不應該破壞使用者熟悉的位置記憶。

### 2.5 回饋要在操作區附近

使用者點哪裡，結果就應該在附近出現。

不要讓使用者：

- 點了上方，結果跑到下方
- 點了卡片，卻不知道下一步在哪裡
- 忘記剛剛選了哪個問題
- 必須記得自己在哪一層

這對降低記憶負荷非常重要。

### 2.6 漸進揭露，而不是一次顯示所有功能

新手需要引導，熟練使用者需要快速路徑。

比較好的做法是：

- 第一層只呈現常用 / 重要項目
- 進階或少用功能放到 More
- 當使用者選到某個問題，再展開對應處置
- 提示要可以略過，不要變成強制教學

---

## 3. v1 版本整理

URL：

https://panstudiollrl-dev.github.io/merry-now-first-prototype/v1.html

### 3.1 v1 的主要目標

v1 的核心目標是驗證：

> Merry 首頁是否可以從「功能控制台」轉成「問題入口」？

它的重點不是讓每個功能都完整，而是確認使用者可以從當下問題開始，而不是從技術功能開始。

### 3.2 v1 的主要內容

v1 包含：

- Now / Default 首頁
- 裝置狀態與左右耳電量
- Comfort volume 控制
- 四張問題卡
- 問題卡選取後的展開式處置卡
- Nearby sound 卡
- Ask someone / care package 流程
- Care Package Ready to Send
- Care Package Sent Confirmation
- Care / More 相關頁面概念

### 3.3 v1 的互動邏輯

第一層有四張主要問題卡：

- I can’t hear clearly
- Won’t connect
- Noise or hiss
- Ask someone

點選問題卡後：

- 卡片本身會變成 selected 狀態
- 下方或同區域會展開對應處置
- 使用者可以返回問題列表
- 不需要再按一次 confirm

### 3.4 v1 的重要設計決策

#### 移除 Confirm 問題按鈕

早期版本曾經有一個類似：

> Confirm: I can’t hear clearly

的按鈕。

後來發現這會造成疑惑，因為它看起來像一個動作按鈕，但實際上只是重述使用者已選的問題。

v1 的修正方向是：

> 點問題卡本身就進入下一層，不再需要額外 confirm。

這是很重要的轉折，因為它讓視覺語意與互動行為一致。

#### Sound Compass 不作為獨立入口

Nearby sound 有被保留，但不作為「Sound Compass tab」。

原因是：

> 使用者不是打開 app 來研究聲音方向，而是因為現在聽覺出了問題。

Nearby sound 應該被包裝成自然的環境提示，而不是要使用者操作的功能。

#### 真人協助放進 Now flow

Ask someone 不是單純的 Care tab。

它應該能把當下情境打包給聽檢師：

- sound environment
- device status
- battery status
- safe setting parameters

使用者不需要自己解釋技術細節。

### 3.5 v1 優點

- 成功建立問題優先的首頁方向
- 四張問題卡清楚、穩定
- 降低了 feature dashboard 的複雜感
- 開始具備高級健康產品的視覺方向
- 舒適音量和左右耳概念已有初步形狀
- Care package 概念有價值

### 3.6 v1 不足

- Merry 還不夠像「會觀察、會回應」的陪伴系統
- 有些區域仍偏靜態說明
- Reconnect 流程還不夠具體
- Nearby sound 還比較像狀態顯示，不夠像處置建議
- 個人化推薦與使用者紀錄尚未進入設計
- Care 相關流程仍容易被理解成另一個 tab 或另一個地方

---

## 4. v2 版本整理

URL：

https://panstudiollrl-dev.github.io/merry-now-first-prototype/v2.html

### 4.1 v2 的主要目標

v2 不是推翻 v1，而是在 v1 的 Now-first 基礎上加入：

> 低干擾、會觀察、會提示、會回饋的陪伴感。

換句話說：

- v1 驗證「問題入口」
- v2 驗證「Merry 是否像一個正在支援你的系統」

### 4.2 v2 的新增重點

v2 新增或強化：

- Merry noticed 動態提示列
- icon-led cues
- scene-aware sound
- busy street 安全提示
- guided reconnect 動態引導
- Personal Listening Space 概念
- v1 / v2 差異說明
- 問卷 placeholder

### 4.3 Merry noticed

v2 加入 Merry noticed 區域，例如：

- Right aid seems weak.
- Speech is nearby.
- Busy street detected.

這些提示不是警報，而是 Merry 溫和地告訴使用者：

> 我注意到一件可能與你現在有關的事。

好的提示應包含：

- icon
- 短句
- 具體下一步
- 不過度打擾

### 4.4 Guided reconnect

v2 在 Won’t connect 裡加入 1-3 step 動態 guide。

目前流程是：

1. Bring aids close
2. Wake right aid
3. Confirm linked

互動方式：

- 點 `Won’t connect`
- 展開 guided reconnect
- 按 `Start guided reconnect`
- Merry 模擬檢查右耳
- 最後顯示 `Both aids are linked.`

這個設計的意義是：

> 不要一次給使用者一堆藍牙排除步驟，而是讓 Merry 一步一步帶著他完成。

未來如果真的串接裝置 API，這裡應該能回饋：

- 好像沒有靠近，再試試看
- 右耳已喚醒
- 現在已連線
- 需要重新配對

### 4.5 Scene-aware sound

v2 開始讓場域辨識不只是資訊，而是處置建議。

目前場景包括：

- Busy street
- Busy table / restaurant
- Clinic / front speech
- Home

例如 busy street 不應只說「現在很吵」，而應該說：

> Merry will keep vehicle and crossing sounds audible while softening harsh background noise.

也就是：

- 降低刺耳噪音
- 但保留交通與安全聲音

這是助聽器 app 很重要的價值。

### 4.6 Personal Listening Space

v2 開始探索個人化音場概念。

這和 Discord Spatial Audio 類似之處是「聲音可以被空間化理解」，但 Merry 的方向不應直接複製多人語音聊天。

Merry 更適合的方向是：

- front speech 靠近
- harsh noise 推遠
- traffic sounds 保留
- care / audiologist 可理解目前聲場
- 使用者知道 Merry 正在保護什麼

這是一個可以往後深入設計的核心概念。

### 4.7 v2 優點

- Merry 開始有陪伴感
- 提示更 icon-led
- 場域安全感更明確
- Reconnect 流程更接近真實使用情境
- 比 v1 更能表現「使用者被支援」
- 仍維持低干擾，不會太吵

### 4.8 v2 不足

- 仍大量基於推測，缺少真實使用者資料
- 個人化推薦還沒有真正實作
- 使用者紀錄尚未進入介面邏輯
- 問卷還只是 placeholder
- icon 是否真的被理解需要測試
- guided reconnect 目前只是模擬，尚未串接真實裝置
- Personal Listening Space 需要更深入研究與法律/專利風險確認

---

## 5. v1 到 v2 的核心轉變

### v1：從控制台轉成問題入口

v1 的問題是：

> 我們能不能不要讓長者面對複雜控制，而是讓他直接說出現在遇到什麼？

所以 v1 的核心是四張問題卡。

### v2：從問題入口轉成陪伴式回應

v2 的問題是：

> Merry 能不能在不打擾的情況下，讓使用者感覺它正在觀察、理解、協助？

所以 v2 加入：

- Merry noticed
- 動態提示
- 圖示
- 場域辨識
- guided reconnect

### v1 降低 decision load

v1 讓使用者不用理解功能分類。

### v2 降低 interpretation load

v2 讓使用者不用自己解讀狀態。

Merry 直接把狀態翻譯成：

- 這件事跟你有關
- 這是為什麼
- 下一步可以做什麼
- 做完後現在變成什麼狀態

### v1 建立問題卡

v1 的問題卡是穩定首頁的基礎。

### v2 在問題卡外圍加入語境

v2 不改掉問題卡，而是在周圍加入 Merry noticed 和 scene-aware cues。

這可以避免首頁過度個人化造成不穩定，同時開始讓 Merry 更聰明。

---

## 6. 已吸收的 UI/UX 書籍與研究概念

### 6.1 使用者不能只用年齡區分

不能只說「長者」或「新手」。

使用者可能是：

- 初次使用者
- 偶爾使用者
- 熟練使用者
- 專家使用者
- 焦慮使用者
- 有聽檢師協助的使用者

介面應該找到不同使用者的交集。

### 6.2 常用選項要凸顯，少用選項要收納

首頁不應該顯示所有功能。

常用或關鍵任務應在第一層：

- 聽不清楚
- 連不上
- 聲音不舒服
- 找人幫忙
- 音量 / 左右耳狀態

少用或專家功能可以進 More。

### 6.3 使用者紀錄很重要

如果有使用紀錄，未來可以用來：

- 推薦常用場景
- 預測常見問題
- 縮短重複操作
- 推薦常用音場設定
- 幫助 care package 更精準

但目前大概率沒有完整資料，所以 v2 先以推測與設計假設建立方向。

### 6.4 記憶負荷要降低

使用者不應需要記得：

- 現在在哪一層
- 剛剛點了哪張卡
- 某個 icon 代表什麼
- 下一步在哪裡

介面應該自然引導下一步。

### 6.5 動態提示可以創造被陪伴感

提示如果做得好，會讓 app 像活的有機體：

- 它注意到我的狀態
- 它知道我可能需要什麼
- 它不強迫我
- 它讓我知道我的操作有效

這是 Merry 未來最重要的產品氣質之一。

### 6.6 視覺設計必須傳遞正確訊息

不要把資訊做成按鈕。

不要讓使用者以為某個東西可以點，但其實只是裝飾。

狀態、提示、按鈕、卡片、流程步驟，都要有明確視覺語意。

---

## 7. 待研究問題

### 7.1 使用者分類

需要研究：

- 台灣助聽器使用者的手機使用習慣
- 年齡、性別、生活型態與 app 使用經驗的關係
- 使用者最常遇到的聽覺困擾
- 使用者何時願意讓 app 自動調整
- 使用者何時需要聽檢師介入

### 7.2 是否需要初次使用問卷

目前傾向：

> 可以有，但不應強迫，也不應太長。

比較好的做法：

- 第一次使用只問最少資訊
- 問卷可以跳過
- 用「幫 Merry 更懂你」的語氣
- 透過使用過程逐步學習

可能詢問：

- 你最常覺得哪裡聽不清楚？
- 餐廳、馬路、家裡、診所，哪個場景最困擾？
- 你希望 Merry 先詢問再調整，還是可以自動建議？
- 是否有聽檢師或家人可以協助？

### 7.3 個人化推薦

未來可以加入：

- Merry often helps you with...
- Suggested for this place
- Last time this helped
- You often ask Dr. Elena about...

但推薦要低干擾，不要佔據主畫面。

### 7.4 專家模式 / 簡易模式

目前不建議一開始就讓使用者選模式。

原因：

- 使用者不一定知道自己是哪種使用者
- 選模式本身也是負擔
- 經驗會變動

更好的做法可能是：

- 第一層保持簡單
- More 裡提供進階控制
- 依照使用紀錄慢慢出現快速路徑

### 7.5 Personal Listening Space 與專利風險

應研究：

- Discord Spatial Audio
- Apple Spatial Audio
- hearing aid directional microphone UI
- spatial hearing personalization
- assistive listening patents

設計上應避免直接複製「拖曳人物到音場位置」的既有模式。

Merry 應該發展自己的語言：

- protect front voice
- keep traffic audible
- soften harsh sound
- move noise farther away
- explain what Merry is protecting

---

## 8. 建議 v3 方向

v3 不應只是加更多頁面。

v3 應該測試：

> Merry 如何在更聰明的同時，仍然保持低干擾？

### 8.1 Adaptive Merry noticed

一次不要超過 1-3 個提示。

排序依據可以是：

- 安全性
- 裝置故障
- speech importance
- 使用者常用行為

### 8.2 更完整的 icon system

需要建立一致 icon 語言：

- 右耳 / 左耳
- 連線
- 電池
- 人聲
- 噪音
- 車流
- 安全
- care / audiologist
- guided step

### 8.3 小型 guided flows

可優先做：

- reconnect right aid
- make speech clearer
- soften harsh noise
- send care package
- keep traffic audible

每個 flow 都應包含：

- 現在 Merry 正在檢查什麼
- 使用者要做什麼
- Merry 是否偵測成功
- 下一步是什麼
- 如何回到 Now

### 8.4 使用者回饋問卷

未來每個版本都應加入問卷。

可測量：

- 是否感覺被支援
- 是否覺得 Merry 太打擾
- 是否找得到需要的功能
- icon 是否比文字更快理解
- 點擊前是否知道下一步會發生什麼
- 是否信任 Merry 的建議
- 是否願意日常使用

---

## 9. 給 Claude / 下一位協作者的提醒

請不要把 Merry 做成：

- 醫療儀表板
- 工程控制台
- 遊戲化介面
- 可愛兒童 app
- 一般健康 app
- 行銷 landing page

請保留：

- Now-first
- Problem-first
- 低干擾
- 陪伴感
- 成熟、清楚、親和的視覺
- Merry 品牌色
- 大而可讀的卡片
- icon-led guidance
- 使用者可反悔
- 人始終能求助

任何新設計請先檢查：

1. 是否降低心智負荷？
2. 是否降低記憶負荷？
3. 是否讓下一步更可預測？
4. 是否避免太多文字？
5. 是否讓 Merry 更像支援者，而不是控制台？
6. 是否保留使用者控制權？
7. 是否避免把資訊做成假按鈕？
8. 是否照顧安全場景？

---

## 10. 一句話總結

v1 證明 Merry 可以從功能控制台轉成問題優先的聽覺求助入口；v2 則開始把這個入口推向一個低干擾、會觀察、會提示、會回饋的陪伴式聽覺支援系統。
