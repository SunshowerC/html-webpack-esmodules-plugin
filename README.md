# html-webpack-esmodules-plugin
为 webpack 打包构建出来的 JS 资源加上 type="module"/nomodule 属性


## Installation
`npm i -D html-webpack-esmodules-plugin`


## Usage
```js
// ...
plugins: [
    new HtmlWebpackPlugin({
        // .... 配置
    }),
    new HtmlWepackEsmodulesPlugin(HtmlWebpackPlugin, {
        isModernBuild: false,
        dynamicInsert: false
    }),
    // ...
]
// ...
```
### options
- isModernBuild:boolean = false
是否是现代化构建。    
设置为 false(默认值) 为 `script` 标签添加上 `nomodule` 属性; 设置为 true 则 为 `script` 标签添加上 `type="module"` 属性。
- dynamicInsert:boolean = false
是否用动态插入标签实现按需加载， 来取代 type="module"/nomodule。    
这是因为部分老版浏览器不能识别 type="module"/nomodule，会把带 type="module" 或者 nomodule 的脚本资源都下载。
