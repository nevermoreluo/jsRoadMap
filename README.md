关于Nodejs库实用习惯的记录

 
### Types
 
##### String  
[Numeral.js](http://numeraljs.com/) 提供字符类型的数值单位转换，货币表示等格式化工具（可以自定义format） 
[Nano](https://github.com/trix/nano) 这其实不是一个库，单纯的是一个string的模版format  
```javascript 1.8
function nano(template, data) {
  return template.replace(/\{([\w\.]*)\}/g, function(str, key) {
    var keys = key.split("."), v = data[keys.shift()];
    for (var i = 0, l = keys.length; i < l; i++) v = v[keys[i]];
    return (typeof v !== "undefined" && v !== null) ? v : "";
  });
}
```


#### Date
[Moment](http://momentjs.com/) 提供日期转换，时区调整等函数 `注意：自带Date类型强转时的时区问题`   


#### Validator
[Validator](https://www.npmjs.com/package/validator) 校验或过滤需要验证的值  
- [Express-validator](https://www.npmjs.com/package/express-validator) 校验express获取的请求值，并给予默认的错误返回，由于express的路由可以添加链式处理，所以校验也可以是链式的

### Tools

#### Data Structure
[Lodash](https://lodash.com) js关于数据结构的组合，拆分，重建，判断，过滤


### Framework

#### Web Service
[Express](http://expressjs.com/)  轻量级网络框架
- [Keystonejs](http://keystonejs.com) 基于Express和Mongoose的网络框架

#### DB Manager （ODM or ORM）
[Mongoose](http://mongoosejs.com/) 看名字就知道了是Mongo数据库的ODM



2018/05/02
