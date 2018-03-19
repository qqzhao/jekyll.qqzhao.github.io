---
layout: post
title: "Promist 有没有await的差别"
# image: header.jpg
video: false
---

Note: Front end JS Promise await/async

* * *

```
try {
    const task1 = async function () {
        console.log('task1')
        return new Promise((resolved, reject) => {
            setTimeout(() => {
                resolved('task1 done')
            }, 2000)
        })
        return 'task1 return'
    }
    
    const test = async function(){
        console.log('begin');
        // let ret = await task1() // 不往下执行，等待
        let ret = task1() // 继续往下执行
        console.log('ret = ', ret);
        console.log('end');
    };
    test();
} catch (e) {
    console.error('e = ', e);
}
```

#### 差别
* 一个需要等待；一个不需要等待，直接往下执行
* 返回结果不一致