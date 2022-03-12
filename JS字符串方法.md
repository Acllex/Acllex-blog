# JS 字符串方法

## 属性

```js
// 字符串长度
string.length;
```

## 方法

1.  **_str.charAt(index);_**

    - 返回下标为 index 的子字符串
    - 返回值：对应下标字符串

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.charAt(5);
    console.log(s); //j
    ```

2.  **_str.charCodeAt(index);_**

    - 根据下标，返回对应下标的字符的 ACSCII 码
    - 返回值: 对应下表字符 ACSCII 码

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.charCodeAt(5);
    console.log(s); //106
    ```

3.  **_String.fromCharCode(十进制 ACSCII 码值);_**

    - 将 ACSCII 码转化成字符串，涉及到数字与字母之间的转化可以使用该方法
    - 返回值: ACSCII 码对应字符串

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = String.fromCharCode(100);
    console.log(s); // d
    ```

4.  **_str.indexOf('要查找的字符串');_**

    - 正序查找一个字符或者字符串在字符串中第一次出现的位置
    - 返回值：目标字符串的下标位置，未找到则为-1

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.indexOf("k");
    console.log(s); // 1
    ```

5.  **_str.lastIndexOf('要查找的字符串');_**

    - 倒序查找一个字符或者字符串在字符串中第一次出现的位置
    - 返回值：目标字符串的下标位置，未找到则为-1

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.lastIndexOf("k");
    console.log(s); // 10
    ```

6.  **_str.replace("原内容","新内容");_**

    - 将指定的字符串替换，只能替换第一个
    - 返回值：返回替换后的字符串
    - 注意：不修改原字符串，所以使用时需要将 replace 方法的返回值保存

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.replace("fkdj", "ab12");
    console.log(s); //fkab12fdjfkdjf
    ```

7.  **_str.slice(起始下标,[结束下标]);_**

    - 字符串截取，识别负数，跟数组相同，参数可以是负数，负数表示倒数，只传一个参数表示从起始下标截取到最后
    - 返回值：返回值是截取到的字符串
    - 注意：截取时，包含起始下标，不包含结束下标； 不修改原字符串

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.slice(3, 7);
    console.log(s); //kdjf
    ```

8.  **_str.substring(起始下标,[结束下标]);_**

    - 字符串截取，同 slice 方法，但不识别负数
    - 返回值：返回值是截取到的字符串

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.substring(3, 7);
    console.log(s); //kdjf
    ```

9.  **_str.substr(起始下标，截取的长度);_**

    - 根据长度进行字符串截取
    - 返回值：返回值是截取到的字符串

    ```js
    let str = "fkfkdjfdjfkdjf";
    let s = str.substr(3, 7);
    console.log(s); //kdjfdjf
    ```

10. **_str.split('需要分割的字符串（可以为空）');_**

    - 以某一字符串将目标字符串分割，可用于将特定格式的字符串转化，如：2018/10/20
    - 返回值： 原字符串呗参数字符串分割之后的数组
    - 注意： 返回值中传入的字符串会被删掉，不修改原字符串

    ```js    
    let str = "2018-12-6"
    let s = str.split("-");
    console.log(s); //["2018", "12", "6"]
    ```

11. **_str.toLowerCase();_**

    - 将 str 字符串中的字符转化为小写，不修改原字符串
    - 返回值：转为小写之后的字符串

    ```js
    let str = "jkjdKJJK";
    let s = str.toLowerCase();
    console.log(s); //jkjdkjjk
    ```

12. **_str.toUpperCase()_**

    - 将 str 字符串中的字符转化为大写，不修改原字符串
    - 返回值：转为大写之后的字符串

    ```js
    let str = "jkjdKJJK";
    let s = str.toUpperCase();
    console.log(s); //JKJDKJJK
    ```

13. **_str.trim()_**

    - 将字符串左右空格去除，可用于接收表单数据 IE9 以下不识别
    - 返回值：去掉左右空格之后的字符串

    ```js
    let str = "hello world";
    let s = str.trim();
    console.log(s); //hello world
    ```

14. **_str.match(字符串或正则表达式)_**

    - 用来检索字符串中的字符
    - 返回值：是一个数组，将检索到的字符放到了这个数组中
    - 注意：如果参数是一个字符，只会检测到第一次出现的字符；如果想要拿到所有的字符需要使用正则表达式（/参数/g(全局)），如果检索的字符不存在，返回 null

    ```js
    let str = "hello world";
    let s = str.match(/o/g);
    console.log(s); //["o", "o"]
    ```

15. **_str.concat('a','b','c')_**

    - 用于连接两个或多个字符串,与数组中的 concat 方法很象，不会修改原字符串
    - 返回值：拼接之后的长字符串

    ```js
    let str = "hello world";
    let s = str.concat(str1);
    console.log(s); //hello world2018-12-6
    ```

16. **_str.padStart() 、str.padEnd()_**

    - 根据给定的字符将字符串补充到指定的长度
    - str.padStart() 在字符串的前面添加
    - str.padEnd() 在字符串的后面添加
    - 参数：1.指定的字符串长度，2.用于补充的字符

    ```js
    let str = "hello world";
    let s = str.padEnd(15, "2019"); //hello world2019
    let s = str.padStart(15, "2019"); //2019hello worl
    console.log(s);
    ```
