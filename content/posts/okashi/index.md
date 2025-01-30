---
title: "算法"
draft: false
summary: "我的一些算法"
tags: ["算法"]
showComments : true
---


## 对称差计算器，支持两个及以上的数组  

```javascript
// 对称差计算器，支持两个及以上的数组
function sym(...a) {
    let args = []
    while(a.length!=1) {
      let c = symmetricDifference(a[0],a[1])
      a.shift()
      a[0]=c
    }
    console.log(a);
    const uniqueArray = [...new Set(a[0])];
    args=uniqueArray
    console.log(args);
    return args;
}
// 计算两个数组的对称差
function symmetricDifference(arr1, arr2) {
  let diff = [];
  for (let i = 0; i < arr1.length; i++) {
      if (!arr2.includes(arr1[i])) {
          diff.push(arr1[i]);
      }
  }
  for (let i = 0; i < arr2.length; i++) {
      if (!arr1.includes(arr2[i])) {
          diff.push(arr2[i]);
      }
  }
  return diff;
}
 
sym([1, 2, 3], [5, 2, 1, 4],[1,2,5]);
```