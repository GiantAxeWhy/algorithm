### 构建链表

```javascript
function node(){
    this.value = value;
    this.next = null;
}
let node1 = new node(1);
let node2 = new node(2);
let node3 = new node(3);
let node4 = new node(4);
node1.next = node2;
node2.next = node3;
node3.next = node4;
```
### 构建栈和队列
`栈像箱子先进后出`
`队列像管子 先进先出`</br>
`1、栈`
```javascript
function Stack(value){
    this.arr = [];
    this.push=function(value){
        this.arr.push(value)
    };
    this.pop=function(){
       return this.arr.pop()
    };
    
};
var stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
stack.pop();

```

`2、队列`

```javascript
    function queue(value){
    let arr = [];
    this.push=function(value){
        this.arr.push(value);
    }
    this.pop = function(){
       return this.arr.shift();
    }
    }
    let queue = new queue();
      queue.push(1);
      queue.push(2);
      queue.push(3);
      queue.pop();
```

### 二叉树
</br>
`前序中序后序，指的是对于中间节点`</br>
 `前序 中间左边右边`</br>
 `中序 左边中间右边`</br>
 `后序 左边右边中间`</br>
 
 ```javascript
    function Node(value){
        this.value=value;
        this.left = null;
        this.right = null;
    };
    let a= new Node('a');
    let b= new Node('b');
    let c= new Node('c');
    let d= new Node('d');
    let e= new Node('e');
    let f= new Node('f');
    
    a.left = b;
    a.right = c;
    b.left = d;
    b.right = e;
    c.left = f;
    
 ```