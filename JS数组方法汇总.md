# JS 数组常用方法汇总

1.  **_arr.push(参数 1,参数 2, ...);_**

    - 给数组最后添加一个或多个元素。
    - 返回值：返回值为添加之后的数组长度。
    - 会修改原数组。

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.push(6);
    console.log(a); // 6
    console.log(arr); // [1,2,3,4,5,6]
    ```

2.  **_arr.unshift(参数 1,参数 2, ...);_**

    - 给数组最前面添加一个或多个元素。
    - 返回值：返回值为添加之后的数组长度。
    - 会修改原数组。

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.unshift(6);
    console.log(a); // 6
    console.log(arr); // [6,1,2,3,4,5]
    ```

3.  **_arr.pop(参数 1,参数 2, ...);_**

    - 删除数组最后一个元素。
    - 返回值：返回值为被删除的元素。
    - 会修改原数组。

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.pop();
    console.log(a); // 5
    console.log(arr); // [1,2,3,4]
    ```

4.  **_arr.shift(参数 1,参数 2, ...);_**

    - 删除数组的第一个元素。
    - 返回值：返回值为被删除的元素。
    - 会修改原数组。

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.shift();
    console.log(a); // 1
    console.log(arr); // [2,3,4,5]
    ```

5.  **_arr.splice(起始位置(下标),被删除的个数,要添加的元素, ...);_**

    - 在任意位置添加或删除数组的一个或多个元素（删除元素可以为 0 个，可以同时删除和添加（先删除，后添加））。
    - 返回值：返回值为被删除的元素（以数组的形式显示）。
    - 会修改原数组。

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.splice(1, 2, 3, 4);
    console.log(a); // [2,3]
    console.log(arr); // [1,3,4,4,5]
    ```

6.  **_arr.join(分隔符);_**

    - 通过分隔符将数组中的数据连接成字符串
    - 返回值：连接好的字符串
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.join("-");
    console.log(a); //1-2-3-4-5
    console.log(arr); //[1,2,3,4,5]
    ```

7.  **_arr.slice(截取的起始下标,结束下标);_**

    - 数组的截取（包含起始下标，不包含结束下标）
    - 返回值：返回值为截取到的数组
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.slice(2, 4);
    console.log(a); //[3,4]
    console.log(arr); //[1,2,3,4,5]
    ```

8.  **_arr.concat(参数 1,参数 2, ...);_**

    - 多个数组的连接（也可以是单个的数据）
    - 返回值：返回值为连接之后的新数组
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let arr1 = [4, 5, 6];
    let a = arr.concat(arr1);
    console.log(a); // [1,2,3,4,5,4,5,6]
    console.log(arr); // [1,2,3,4,5]
    ```

9.  **_arr.forEach((callback(回调函数))function(value(数组的元素),index(数组的下标),arr(数组本身，可省略不写) ){},this);_**

    - 遍历数组（在 forEach 方法的 callback 回调函数中有三个参数，分别是数组的元素、数组的下标、数组本身）
    - 返回值：没有返回值
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    arr.forEach((r, i) => {
      console.log(r, i);
    }, this);
    ```

10. **_arr.indexOf(值);_**

    - 正序查找
    - 返回值：如果存在返回值所对应的下标，为如果存在返回值为-1
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.indexOf(4);
    console.log(a); // 3
    console.log(arr); // [1,2,3,4,5]
    ```

11. **_arr.lastIndexOf(值);_**

    - 倒序查找
    - 返回值：如果存在返回值所对应的下标，为如果存在返回值为-1
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.lastIndexOf(4);
    console.log(a); // 3
    console.log(arr); // [1,2,3,4,5]
    ```

12. **_arr.sort([回调函数]);_**

    - 数组的排序（参数：不传参数按找数组元素的 ACSCII 的大小值排列（一般为升序），如果传递参数必须为回调函数，回调函数中有两个参数，（分别为参数 1，参数 2；升序排列：return: 参数 1 - 参数 2; 降序排列：return: 参数 2 - 参数 1; ）根据回调函数返回值的结果进行排序）
    - 返回值：返回值为排序后的数组
    - 会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.sort((a, b) => {
      return b - a;
    });
    console.log(a); // [5,4,3,2,1]
    console.log(arr); // [5,4,3,2,1]
    ```

13. **_arr.filter((callback(回调函数))function(value(数组的元素),index(数组的下标),arr(数组本身，可省略不写) ){},this);_**

    - 数组的筛选（筛选数组中满足条件的数据，将筛选出来的数据放在一个新数组中）
    - 返回值：返回值为筛选之后的数组
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.filter((value, index) => {
      return value < 4;
    });
    console.log(a); // [1,2,3]
    console.log(arr); // [1,2,3,4,5]
    ```

14. **_arr.map((callback(回调函数))function(value(数组的元素),index(数组的下标),arr(数组本身，可省略不写) ){},this);_**

    - 数组的映射（将回调函数每次的返回值，组成一个新的数组）
    - 返回值：返回值为映射改变之后的数组
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.map((value, index) => {
      return value * 3;
    });
    console.log(a); // [3,6,9,12,15]
    console.log(arr); // [1,2,3,4,5]
    ```

15. **_arr.some((callback(回调函数))function(value(数组的元素),index(数组的下标),arr(数组本身，可省略不写) ){},this);_**

    - 根据回调函数的判断条件来选择真假
    - 返回值：只要有一个回调函数返回值是 true，最终 some 结果是 true；
    - 不会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.some((value, index) => {
      return value < 3;
    });
    console.log(a); // true
    console.log(arr); // [1,2,3,4,5]
    ```

16. **_arr.every((callback(回调函数))function(value(数组的元素),index(数组的下标),arr(数组本身，可省略不写) ){},this);_**
    - 根据回调函数的判断条件来选择真假
    - 返回值：只要有一个回调函数返回值是 false，最终 every 结果是 false；
    - 不会修改原数组
    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.every((value, index) => {
      return value < 3;
    });
    console.log(a); // false
    console.log(arr); // [1,2,3,4,5]
    ```
17. **_arr.reverse();_**

    - 数组的翻转
    - 返回值：返回值为修改后的数组
    - 会修改原数组

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let a = arr.reverse();
    console.log(a); // [5,4,3,2,1]
    console.log(arr); // [5,4,3,2,1]
    ```

18. **_Array.from(对象);_**

    - 这个方法可以将类数组对象或者能够遍历对象转为一个真正的数组

    ```js
    let obj = {
      0: 1,
      1: 2,
      2: 3,
      length: 3,
    };
    let arr = Array.from(obj);
    console.log(arr); // [1,2,3]
    ```

19. **_Array.of(参数 1,参数 2, ...);_**

    - 用于将传递的参数（参数可以是任意数据类型）放置到一个数组中，如果没有参数，返回的是一个空数组

    ```js
    let arr = Array.of(1, 2, 3, 4, 5);
    console.log(arr); // [1,2,3,4,5]
    ```

20. **_arr.includes(需要查找的数据,起始下标（可省略）) ;_**

    - 用于检查数组是否包含某元素（不能判断对象是否存在）
    - 返回值：返回值为布尔值，如果存在为 true，如果不存在为 false
    - 不会修改原数组

    ```js
    let arr = [1, 2, 3, 4, 5];
    let a = arr.includes(3);
    console.log(a); // true
    console.log(arr); // [1,2,3,4,5]
    ```

21. **_arr.fill(内容，起始下标(可省略),结束下标(可省略))_**

    - 用一个固定值填充一个数组中从起始索引到终止索引内的全部元素，不包括终止索引
    - 返回值：没有返回值
    - 会修改原数组

    ```js
    const array1 = [1, 2, 3, 4];
    // fill with 0 from position 2 until position 4
    console.log(array1.fill(0, 2, 4)); // [1, 2, 0, 0]

    // fill with 5 from position 1
    console.log(array1.fill(5, 1)); // [1, 5, 5, 5]

    console.log(array1.fill(6)); // [6, 6, 6, 6]
    ```
