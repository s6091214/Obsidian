# Terminal 指令

## 基本操作 / 系統

| 指令                          | 說明                  |
| --------------------------- | ------------------- |
| `help [command]`            | 顯示幫助，或指定指令說明        |
| `alias [-g] [name="value"]` | 建立或顯示 Terminal 別名   |
| `unalias [alias name]`      | 刪除指定別名              |
| `history [-c]`              | 顯示或清空 Terminal 歷史紀錄 |
| `clear` / `cls`             | 清除 Terminal 畫面      |
| `hostname`                  | 顯示目前主機名稱            |
| `home`                      | 回到 home 電腦          |
| `changelog`                 | 顯示更新紀錄              |

## 檔案管理

|指令|說明|
|---|---|
|`ls [dir] [--grep pattern]`|列出目錄檔案|
|`cd [dir]`|切換資料夾|
|`cp [src] [dest]`|複製檔案|
|`mv [src] [dest]`|移動 / 改名檔案|
|`rm [file]`|刪除檔案|
|`cat [file]`|顯示文字或文學檔案內容|
|`nano [files...]`|編輯檔案|
|`vim [files...]`|編輯檔案（Vim 模式）|
|`download [file]`|下載腳本或文字檔到本地|
|`scp [files...] [server]`|複製檔案到遠端伺服器|
|`wget [url] [target file]`|從網址抓檔案|


## 腳本 / 程式操作

| 指令                                                          | 說明           |
| ----------------------------------------------------------- | ------------ |
| `run [script] [-t n] [--tail] [--ram-override n] [args...]` | 執行腳本或程式      |
| `kill [script/pid]`                                         | 停止指定腳本       |
| `killall`                                                   | 停止本機所有腳本     |
| `ps`                                                        | 顯示正在運行的腳本    |
| `top`                                                       | 顯示腳本 RAM 使用量 |
| `tail [script/pid] [args...]`                               | 顯示腳本即時輸出     |
| `mem [script] [-t n]`                                       | 顯示腳本所需 RAM   |
| `check [script] [args...]`                                  | 查看腳本日誌       |

## 伺服器 / 網路操作

| 指令                      | 說明                   |
| ----------------------- | -------------------- |
| `scan`                  | 列出當前可連接的伺服器          |
| `scan-analyze [d] [-a]` | 顯示距離 d 範圍內伺服器資訊      |
| `connect [hostname]`    | 連線到遠端伺服器（遊戲特有）       |
| `sudov`                 | 顯示是否有 root 權限        |
| `backdoor`              | 安裝後門（需要 root）        |
| `analyze`               | 分析當前伺服器狀態（錢、RAM、安全性） |

## 駭客專用 / 目標操作

| 指令                    | 說明                              |
| --------------------- | ------------------------------- |
| `hack`                | 從伺服器偷錢（增加安全性）                   |
| `grow`                | 增加伺服器金錢（增加安全性）                  |
| `weaken`              | 降低伺服器安全性                        |
| `buy [-l/-a/program]` | 從 Dark Web 購買程式（如 BruteSSH.exe） |
##  工具 / 運算

| 指令                              | 說明             |
| ------------------------------- | -------------- |
| `expr [math expression]`        | 計算數學表達式        |
| `free`                          | 查看本機 RAM 使用情況  |
| `lscpu`                         | 顯示 CPU 核心數     |
| `grep [opts]... pattern [file]` | 搜尋檔案中的文字或正則表達式 |



# 新手教學（CSEC）

## **目標**

取得 **CSEC** 伺服器的 **root 權限**，這樣你才能開始偷錢和練習自動化腳本。

## 流程圖概覽
```
開始 → 賺第一桶金 → scan + connect → 嘗試 NUKE
      ↓           ↓
    成功? ← 否 → hack 其他低等級伺服器
      ↓
   Root Access: YES → analyze 查看伺服器狀態
      ↓
   weaken 降低安全性 → hack 偷錢
      ↓
   可以自動化 → 寫腳本控制 hack/grow/weaken
      ↓
   Hacknet Nodes → 增加被動收入
      ↓
   City 找工作 → 增加收入
      ↓
   購買 TOR → buy 工具 → 打開端口
      ↓
   安裝 Backdoor → 永久存取伺服器

```

## **步驟教學**

### 1️⃣ 賺第一桶金

- 在取得 CSEC root 之前，你需要先有點錢。
- scan 先查詢附近主機。
- connect 連過去。
- 可以 hack 離你最近的低等級伺服器（像 `foodnstuff`）賺錢。

### 2️⃣ 找到並連線到伺服器

1. 用 `scan` 查找附近主機。
    
2. 用 `connect 伺服器名稱` 連過去。
    
3. 嘗試用 `NUKE.exe` 獲取 root 權限。
    
4. 如果失敗 → 先 hack 其他容易的伺服器賺錢。

### 3️⃣ 確認是否成功

- 成功後輸入：
```
	analyze
```
- 出現 `Root Access: YES` → 代表你已經有 root 權限，可以自由操作這台伺服器。
  
### 4️⃣ 提高 hack 成功率

- hack 成功率一開始通常很低
    
- 先降低伺服器安全性：
```
weaken
```
- 不停地 weaken，直到成功率足夠高，再去偷錢：
```
  hack
```

### 5️⃣ 自動化腳本

[文檔](https://github.com/bitburner-official/bitburner-src/blob/stable/markdown/bitburner.ns.md)

- `nano或vim test.js` → 建立腳本
    
- 使用迴圈控制：
    
    - hack → 偷錢
        
    - grow → 補滿金額
        
    - weaken → 降低安全性
        
- 注意 RAM 使用量

### 6️⃣ 被動收入

- Hacknet Nodes → 自動產生金錢
    
- 多餘錢可以升級 Hacknet 或買工具
  
### 7️⃣ 賺更多錢

- 去 City 找工作 → 增加收入
    
- 購買 TOR → 才能用 `buy -l` 查看工具
    
- 工具例：`BruteSSH.exe` → 打開 SSH 端口

### 8️⃣ 打開端口

- 用 `BruteSSH.exe` 可以打開 SSH 端口
    
- 其他工具還有 FTPCrack、HTTPWorm 等，後續伺服器需要多個端口才能 NUKE

### 9️⃣ 安裝 Backdoor

- 安裝後門可以讓你永久遠端存取這台伺服器
    
- 安裝條件：駭客等級達到需求
    
- 使用：
```
  backdoor
```
- 可以用 `analyze` 查看是否符合需求

## **腳本相關小技巧**

- `ns.args` 可以讓腳本接受 **外部傳入的參數**
    
- `ns.tprint()` → 在 Terminal 顯示訊息
    
- `ns.print()` → 在腳本 log 中輸出訊息
    
- 記得控制 **RAM 使用量**，超過容量腳本就執行不動
  
  
  # Factions 介紹（Bitburner）

## 什麼是 Factions？

Factions 是 Bitburner 世界中的組織。玩家可以透過完成條件加入不同的 Faction，並在其中賺取聲望（Reputation）。聲望能用來購買特殊的 **Augmentations（強化）**，這些會永久提升角色的能力，並在轉生（Augmentation 安裝後重啟）後保留。

---

## 如何加入 Factions？

加入 Faction 的條件有幾種：

- **駭入伺服器**：有些需要安裝 backdoor（例：CSEC）。
    
- **金錢門檻**：資產達到一定金額會收到邀請。
    
- **城市地點**：在特定城市工作或生活一段時間。
    
- **公司工作**：在某些公司工作一段時間。
    
- **特殊事件**：隨劇情或玩家行為觸發。
    

---

## 為什麼要加入 Factions？

1. **購買 Augmentations**：遊戲中最重要的提升來源。
    
2. **聲望養成**：越高的聲望能解鎖越強的 Augmentations。
    
3. **多樣化的玩法**：不同 Faction 偏向駭客、戰鬥、公司路線，提供不同方向的強化。
    

---

## 舉例

- **CyberSec**：需要在 `CSEC` 伺服器安裝 backdoor 才能加入，提供駭客向 Augmentations。
    
- **NiteSec**：同樣以駭客為主。
    
- **MegaCorp / ECorp**：要在這些大公司工作才會獲得邀請。
    
- **城市幫派 Factions**：如 Slum Snakes，要求有一定金錢並位於特定城市。
    

---

## 總結

Factions 是玩家進入中後期的核心玩法。**目標是累積聲望 → 購買 Augmentations → 重生 → 變得更強 → 加入更多強大 Factions。**