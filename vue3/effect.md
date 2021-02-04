effect

收集每个key修改时需要触发的函数

```javascript
// 容器
const targetMap = new WeakMap()

const effectStack = []
let activeEffect;

export function isEffect(fn) {
   return fn && fn._isEffect === true
}

export function effect(
   fn,
   options = {}
) {
   // 如果是effect, 指向原始函数
   if(isEffect(fn)) {
      fn = fn.raw
   }
   const effect = createReactiveEffect(fn, options)
   
}
```