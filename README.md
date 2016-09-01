###1.  在你系统有涉及到nodejs, 那你肯定很喜欢做一件事情就是后台的数据交互跟前段页面拉取数据渲染了
  1.  第一部 查询页面报错如果出现XML的字样，证明你的数据格式出错了，就是在跨域请求的时候 数据访问不到，无法获取，渲染不到你的web页面
  2.  在你的app.js 里面写下下面这行代码。 具体意思就不过多解释了，主要是解决有使用node.js的时候来使用的。 
```javascript
        app.all('*', function(req, res, next) {      res.header("Access-Control-Allow-Origin", "*");      res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");      res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS");      res.header("X-Powered-By",' 3.2.1')      res.header("Content-Type", "application/json;charset=utf-8");      next();  });
```
