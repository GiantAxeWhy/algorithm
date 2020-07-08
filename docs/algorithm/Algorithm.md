
### 链表的逆置
```javascript
function Node(value) {
    this.value = value;
    this.next = null;
}

var node1 = new Node(1);
var node2 = new Node(2);
var node3 = new Node(3);
var node4 = new Node(4);
var node5 = new Node(5);

node1.next = node2;
node2.next = node3;
node3.next = node4;
node4.next = node5;

function nizhi(){
    if(root.next.next === null){
        root.next.next = root;
        return root.next;
    }else{
        let result = nizhi(root.next);
        root.next.next = root;
        root.next = null;
        return result
    }
};
    var nextRoot = nizhi(node1);
    function blan(root){
        if(root === null)return;
        blan(root.next)
    }
    blan(nextRoot);
```


### 冒泡排序
1、
```javascript
var arr = [4,1,6,9,3,2,8,7];

function getMin(arr){
    if(arr ===null&&arr.length ==0)return ;
    let index = -1;
    for(let i = 0 ; i<arr.length;i++){
        if(arr[i] !=null && arr[i]<arr[index] || arr[i] != null && index == -1){
            index = i
        }
    }
    let result = arr[index];
    arr[index] = null;
   return result ;
}
function sort(arr){
    let resultArr = new Array(arr.length)
    for(let i =0;i<arr.length;i++){
      resultArr[i] = getMin(arr[i])
    }
    return resultArr
}
console.log(sort(arr));
```
2、

```javascript
var arr = [4,1,6,9,3,2,8,7];
function compare(a,b){
    if(b<a)return true;
    else return false
}
function change(arr,a,b){
    let temp = arr[a];
    arr[a] = arr[b];
     arr[b] = temp 
}
function sort(arr){
    for(let i = 0 ; i<arr.length;i++){
          for(let j = 0 ; j<arr.length -1 ;j++){
                if(compare(arr[j],arr[j+1])){
                    change(arr,j,j+1)
                }
            }
    }
  
}
sort(arr);
console.log(arr);
```

### 选择排序
选择排序，内层循环，每一圈选出一个最大的，然后放在后面
```javascript
    var arr = [4,1,6,9,3,2,8,7];
    function compare(arr,a,b){
        if(a<b)return true;
        else return false
    }
    function change(arr,a,b){
        let temp = arr[a];
        arr[a]= arr[b];
        arr[b] = temp;
    }
    function sort(arr){
        for(let i = 0 ; i<arr.length;i++){ 
                let maxIndex  =0;            
               for(let j = 0 ;j<arr.length-i-1;j++){
                        if(compare(arr,arr[i],arr[j])){
                            maxIndex = j
                        }
                    }
                    change(arr,maxIndex,arr.length - 1 - i)
        }
     
    }
```

### 快速排序
选个值 移动左右指针比他小的放左边 比它大的放右边
```javascript
var arr = [4,1,6,9,3,2,8,7];
function change(arr,a,b){
    let temp  = arr[a];
    arr[a] = arr[b];
    arr[b]=temp;
}
function sort(arr,begin,end){
    if(begin>=end-1)return ;
    let left = begin,right=end;
    do{
       do left++ ;while(left<right&&arr[left]<arr[begin]); 
       do right++ ;while(left<right&&arr[begin]<arr[right]); 
       if(left<right)change(arr,left,right)
    }while(left<right)
    let swaper = left ===right?right -1:right;
    change(arr,begin,swaper);
    sort(arr,begin,swaper)
    sort(arr,swaper+1,end)
}
function quickSort(arr) {
    sort(arr, 0, arr.length);
}
quickSort(arr);
console.log(arr);

```