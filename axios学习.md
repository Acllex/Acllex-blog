# axios 用法

## 默认配置

```js
// 全局 axios 默认值

// 全局api url
axios.defaults.baseURL = "https://api.com";
// 全局的post请求头
axios.defaults.headers.post["Content-Type"] =
  "application/x-www-form-urlencoded";
/*
 * Content-Type: application/json ： 请求体中的数据会以json字符串的形式发送到后端
 * Content-Type: application/x-www-form-urlencoded：请求体中的数据会以普通表单形式（键值对）发送到后端
 * Content-Type: multipart/form-data： 它会将请求体的数据处理为一条消息，以标签为单元，用分隔符分开。既可以上传键值对，也可以上传文件。
 */

// 开启跨域支持
axios.defaults.withCredentials = true;
```

## axios api

```js
// axios(config)

// 发起一个get请求
axios("/user/12345");

// 发起一个post请求
axios({
  method: "post",
  url: "/user/12345",
  data: {
    firstName: "Fred",
    lastName: "Flintstone",
  },
});

// 请求方式别名

axios.request(config)
axios.get(url[, config])
axios.delete(url[, config])
axios.head(url[, config])
axios.options(url[, config])
axios.post(url[, data[, config]])
axios.put(url[, data[, config]])
axios.patch(url[, data[, config]])
```

## 拦截器

```js
// 添加请求拦截器
axios.interceptors.request.use(
  function (config) {
    // 在发送请求之前做些什么
    // 添加token
    config.headers.token = token;
    return config;
  },
  function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  }
);

// 添加响应拦截器
axios.interceptors.response.use(
  function (response) {
    // 2xx 范围内的状态码都会触发该函数。
    // 对响应数据做点什么
    return response;
  },
  function (error) {
    // 超出 2xx 范围的状态码都会触发该函数。
    // 对响应错误做点什么
    return Promise.reject(error);
  }
);
```
