
### 定義

DFS 是一種圖或樹遍歷算法，特點是「沿著一條路一直走到底，再回頭探索其他路」。

### 特點

- 使用 **遞迴或堆疊（Stack）** 實作。
    
- 遍歷順序：先沿某條路徹底探索，再回頭探索其他路。
    
- 深度優先。
    

### 優點

- 程式碼簡單、直覺。
    
- 適合需要完全探索整個圖的情況。
    

### 缺點

- 節點很多時，可能爆遞迴堆疊。
    
- 找最短路徑不方便。
    

### 範例（伺服器掃描）

```javascript
function scanAll(ns, server, visited = new Set()) {
    visited.add(server);
    for (const neighbor of ns.scan(server)) {
        if (!visited.has(neighbor)) {
            scanAll(ns, neighbor, visited);
        }
    }
    return visited;
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

- DFS 遍歷順序：home → srv1 → srv3 → srv4 → srv2