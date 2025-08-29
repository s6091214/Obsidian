
### 定義

Queue 是一種 **先進先出（FIFO, First-In-First-Out）** 的資料結構，元素按照加入順序排隊，最早加入的元素最先被取出。

### 特點

- **先進先出**：最先加入的元素最先被處理。
    
- 支援兩個主要操作：
    
    - `enqueue`（入隊）：將元素加入隊列尾。
        
    - `dequeue`（出隊）：將隊列頭的元素取出。
        
- 常用於需要順序處理的場景。
    

### 優點

- 簡單明瞭，操作固定。
    
- 適合任務排程、廣度優先搜尋（[[BFS（Breadth-First Search，廣度優先搜尋）]]）、事件處理等場景。
    

### 範例（JavaScript 實作）

```javascript
class Queue {
    constructor() {
        this.items = [];
    }

    // 入隊
    enqueue(element) {
        this.items.push(element);
    }

    // 出隊
    dequeue() {
        if(this.isEmpty()) return null;
        return this.items.shift();
    }

    // 取得隊列頭元素
    front() {
        return this.isEmpty() ? null : this.items[0];
    }

    // 判斷是否為空
    isEmpty() {
        return this.items.length === 0;
    }

    // 取得隊列大小
    size() {
        return this.items.length;
    }
}

// 使用範例
const queue = new Queue();
queue.enqueue('home');
queue.enqueue('srv1');
console.log(queue.dequeue()); // home
console.log(queue.front());   // srv1
```