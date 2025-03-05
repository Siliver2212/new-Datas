# new-Datas

####
1、IndexedDB 是一个浏览器内建的数据库，
类似本地存储localstore，但是相比localStore 10MB的存储量大的多
默认情况下，浏览器会将自身所在的硬盘位置剩余容量全部作为indexedDB的存储容量。
2、在indexedDB中，需要有一个唯一的标识符来区分存储的内容，的是id，这表示，存储的每一个值内都需要一个唯一的id值，这是第二个特点，统一的唯一标识符（key）
3、树形结构的对象存储
4、indexedDB遵循同源协议(只能访问同域中存储的数据，而不能访问其他域的)

####
1、普通盒模型和怪异盒模型有什么区别？
标准盒模型是 CSS 中默认的盒模型。它由（content）、（padding）、（border）（margin）四部分组成。
怪异盒模型：其特点是元素的宽度和高度包含了内边距和边框。

####
2、块元素和行内元素区别是什么？常见块元素和行内元素有哪些？
块元素：默认占据一行，可以设置宽度、高度、内边距和外边距，可以包含其他块级元素和行内元素。
行内元素： 不会独占一行，宽度和高度由内容决定，无法设置宽度和高度

#### 代码优化
    HTML 优化
        精简 HTML 代码
        减少 iframes 使用，延迟加载 iframe，父文档加载完毕后再给 iframe 的 src 赋值
        压缩空白符
        避免节点深层级嵌套
        避免 table 布局
        删除注释
        CSS&Javascript尽量外链
        删除元素默认属性
        #CSS 优化

    css 优化
        尽量减少样式层级数量


#### webpack优化
    引入 webpack-bundle-analyzer 分析打包后的文件，判断哪些包还可以拆分和优化。

    webpack自身的优化：
        tree-shaking，在生产环境下，会自动移除没有使用到的代码
        scope hosting 作用域提升，变量提升，可以减少一些变量声明
        babel 配置的优化，配置 @babel/plugin-transform-runtime，重复使用 Babel 注入的帮助程序，以节省代码大小的插件。

    项目组件开发：我们会在webpack的entry，path.join一个js文件，并命名好。脚本构建后打包的jar才会有这个js，然后通过运维部署到服务器上
    独立页面开发：new HTMLPlugins 设置好html，打包后就会含有改html，用ngix映射到这个html，

devServer => proxyconfig 设置需要识别的context，


#### 
    Cookie：适用于需要跨域访问或持久化存储少量数据的场景。(4KB) 关闭浏览器就失效；
    LocalStorage（长期数据存储）：适用于需要持久化存储较大数据的场景。（5M）; 永久
    SessionStorage（临时数据存储）：适用于需要临时存储较大数据且不需要跨页面的数据的场景。(5M); 闭浏览器窗口或标签页，数据就会被清除

####
    ‌哈希模式‌：刷新页面不会触发服务器请求，浏览器只重新加载当前页面。
    ‌history模式‌：刷新页面会导致新的请求发送到服务器，服务器需要返回对应的页面内