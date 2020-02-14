# Travel website

> A Vue.js project：采用组件化思想搭建整个项目，从而使组件高度复用。
## 技术栈
- vue: 实现SPA单页应用
- vue-router：搭建项目路由
- vuex：实现单文件组件和数据的抽离
- webpack：vue-cli搭建，配置第三方插件

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

## 项目演示
![img](https://ae01.alicdn.com/kf/U48610c9cccfa45fa925b745a3ffa6845J.gif)

## 使用vue优化总结

### 代码review

- v-if和v-show作用区分，注意使用场景
    - v-if：真正意义上的条件判断，当条件为false，dom不渲染。当数据不是经常变化，使用它（不过还需要注意，dom数量少的时候，能提高首屏渲染时间，基于现实中的应用判断选择哪个合适）
    - v-show：只是display为none和无的区别。当数据经常变化时使用，性能提高，因为dom，不会经常增删，减少重排。
- style标签要加上scoped
    - 仅在当前作用域有效。这样在当前作用域内的定义的简短样式变量不用担心跟共同开发人员撞了
- template的应用
    - 模板中dom元素的判断减少过多js表达式，最好写到computed里封装成方法。如果这个判断有多个元素需要，就可以调用一个方法
    - 为item设置唯一的值：保证vue最快且精确找到数据，官网如下说，当state更新时，新的状态值和旧的状态值对比，较快的定位到diff
- computed和watch区分使用场景
    - computed：计算属性，只有它所依赖的属性值发生该百年，才会重新计算computed。做一层filter，切忌加入调用方法
    - watch：监听数据变化去改变数据或触发事件。当需要执行异步或运算时间较长的方法，使用watch。
- 组件要多拆分，组件分的越细后期维护会更轻便
- 页面中的展示数据设置Object-freeze限制数据监听
    - 服务器返回的数据量较大时能提高性能，这样vue不会去监听数据的变化
- 全局事件最好要销毁
    - 组件本身的事件vue会进行销毁，但是全局事件还是需要移除事件监听（这是项目遇见的坑！）
- 合理使用组件缓存keep-alive
- 路由的懒加载
    - 在该项目的路由配置文件 router-> index.js引用组件（项目简单可使用同步组件，因为这样只有一个http请求，但项目复杂性能更优，一般打包后项目首屏加载文件大于1M，则应该使用异步组件）
    - 设置异步组件，实现按需加载文件，项目打包不会把所有js包放在app.js里
    - 但一定要注意哪些地方需要使用异步组件，比如说首页内容要同步加载，但是首页里的内容对应的tab可以动态加载
    - 语法：() => import( //路由路径) --> 返回promise

### webpack优化

- 减少代码查找：利用alias
    - bulid-> webpack.base.conf.js -> resolve.alias 创建import和require的别名，确保模块引入变得简单。
- 图片压缩
    - 在url-loader中设置limit对图片做了限制，小于limit的图片转化为base64格式。这是vue-cli做好的一部分
    - 图片资源还是非常大，可以使用image-webpack-loader来压缩图片。通过npm安装，设置loader: image-webpack-loader，options.bypassOnebug=true
- 使用CommonsChunkPlugin插件来提取多个页面使用的公共代码
    - 作用：建立一个包括多个入口chunk的公共模块的独立文件。
    - 配置方法: https://webpack.docschina.org/plugins/commons-chunk-plugin/#%E9%85%8D%E7%BD%AE

### get：HTML内实现Loading

借助html-webpack-plugin将一段指定的html和css插入到模板中，在ajax未返回数据，页面展示loading  
具体做法：
- 将loading效果的html拆分成loading.html & loading.css
- 放在/src/preLoad/loading.html | loading.css

webpack.config读取文件
```
module.exports = {
  loading: {
    html: fs.readFileSync(path.join(__dirname, '../src/preLoad/loading.html')),
    css: '<style>' + fs.readFileSync(path.join(__dirname, '../src/preLoad/loading.css')) + '</style>'
  }
  // ...
}
```
bulid配置
```
module.exports = {
  plugins: [
    new HtmlWebpackPlugin({
      loading: config.loading
      // ...
    })
    // ...
  ]
  // ...
}
```
引用：<%= htmlWebpackPlugin.options.loading.html| loading.css %>



For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
