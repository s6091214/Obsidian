
### 定義

BFS 是一種圖或樹遍歷算法，特點是「先橫向掃描同一層節點，再往下一層」。

### 特點

- 使用 **隊列（Queue）** 實作。
    
- 遍歷順序：先掃描離起始節點最近的節點，再往更遠的節點掃描。
    
- 一層一層遍歷。
    

### 優點

- 不會爆堆疊，適合節點很多的圖。
    
- 可以找到最短路徑或最近的目標。
    
- 遍歷順序穩定，容易 debug。
    

### 範例（伺服器掃描）

```javascript
function getAllServers(ns, start = "home") {
    const visited = new Set([start]);
    const queue = [start];

    while (queue.length) {
        const server = queue.shift();
        for (const neighbor of ns.scan(server)) {
            if (!visited.has(neighbor)) {
                visited.add(neighbor);
                queue.push(neighbor);
            }
        }
    }

    return [...visited];
}
```

### 遍歷順序示意

```
        home
       /    \
     srv1   srv2
    /   \
  srv3  srv4
```

- BFS 遍歷順序：home → srv1 → srv2 → srv3 → srv4


### 1. `visited` 的作用

- `visited` 只是 **記錄哪些伺服器已經看過了**，避免重複掃描。
    
- 如果你只用 `visited`，你知道自己看過哪些伺服器，但不知道 **下一步要掃描哪個伺服器**。
    

---

### 2. `queue` 的作用

- `queue` 是 **待掃描伺服器的列表**。
    
- BFS 的邏輯：**先掃描離 home 最近的節點，再掃描下一層**。
    
- 當你掃描一個伺服器時，把它的鄰居加入 queue，確保下一次迴圈會去掃描這些鄰居。
    
- 沒有 queue，你就無法按層次順序掃描，只能停留在當前節點。
    

---

### 3. 比喻

想像你要拜訪一棟大樓的每個房間：

- `visited` = 你已經進過的房間，避免重複進。
    
- `queue` = 你現在排隊要進的房間列表。
    
    - 你進一個房間，看到它的鄰居，把沒去過的鄰居排進隊列。
        
    - 下一輪就從隊列取出下一個房間去拜訪。
        

如果沒有 queue，你就沒有辦法記住「還有哪些房間沒進」，就無法完成整棟樓的遍歷。

---

### 4. 小結

- **visited**：防止重複掃描。
    
- **queue**：控制 BFS 遍歷順序，確保每層都掃描到。