# JS 数组常用方法汇总

1. **_arr.push(参数 1,参数 2, ...);_**

   - 给数组最后添加一个或多个元素。
   - 返回值：返回值为添加之后的数组长度。
   - 会修改原数组。

```javascript
let arr = [1, 2, 3, 4, 5];
let a = arr.push(6);
console.log(a); // 6
console.log(arr); // [1,2,3,4,5,6]
```

2. **_arr.unshift(参数 1,参数 2, ...);_**

   - 给数组最前面添加一个或多个元素。
   - 返回值：返回值为添加之后的数组长度。
   - 会修改原数组。

```javascript
let arr = [1, 2, 3, 4, 5];
let a = arr.unshift(6);
console.log(a); // 6
console.log(arr); // [6,1,2,3,4,5]
```

3. **_arr.pop(参数 1,参数 2, ...);_**

   - 删除数组最后一个元素。
   - 返回值：返回值为被删除的元素。
   - 会修改原数组。

```javascript
let arr = [1, 2, 3, 4, 5];
let a = arr.pop();
console.log(a); // 5
console.log(arr); // [1,2,3,4]
```

4. **_arr.shift(参数 1,参数 2, ...);_**
   - 删除数组的第一个元素。
   - 返回值：返回值为被删除的元素。
   - 会修改原数组。

```javascript
let arr = [1, 2, 3, 4, 5];
let a = arr.shift();
console.log(a); // 1
console.log(arr); // [2,3,4,5]
```

5. **_arr.splice(起始位置(下标),被删除的个数,要添加的元素, ...);_**
   - 在任意位置添加或删除数组的一个或多个元素（删除元素可以为 0 个，可以同时删除和添加（先删除，后添加））。
   - 返回值：返回值为被删除的元素（以数组的形式显示）。
   - 会修改原数组。

```javascript
let arr = [1, 2, 3, 4, 5];
let a = arr.splice(1, 2, 3, 4);
console.log(a); // [2,3]
console.log(arr); // [1,3,4,4,5]
```
