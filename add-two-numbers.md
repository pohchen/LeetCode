## Add Two Numbers  [link](https://leetcode.com/problems/add-two-numbers/)

> You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their > nodes contain a single digit. Add the two numbers and return it as a linked list.

> Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
> Output: 7 -> 0 -> 8

```javascript 
function ListNode(val) {
  this.val = val;
  this.next = null;
}
var addTwoNumbers = function(l1, l2) {
  var next1 = l1.next;
  var next2 = l2.next;
  var sum = l1.val + l2.val;
  
  var l3 = new ListNode(sum%10)
  var node = l3;
  var sum = Math.floor(sum/10);
  
  while(next1 || next2 || sum!==0){
        sum = sum + (next1?next1.val:0)+(next2?next2.val:0);
        node.next = new ListNode(sum%10);
        node = node.next;
        next1 = next1?next1.next:null;
        next2 = next2?next2.next:null;
        sum = Math.floor(sum/10);
  }
  return l3;
};

```


Testing data
```javascript 
var a3 = new ListNode(3);
var a2 = new ListNode(4);  a2.next = a3;
var a1 = new ListNode(2);  a1.next = a2;

var b3 = new ListNode(4);
var b2 = new ListNode(6);  b2.next = b3;
var b1 = new ListNode(5);  b1.next = b2;

console.log(addTwoNumbers(a1, b1));
```
