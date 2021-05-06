# Webpack

### 主要结构

**1、入口：entry**

项目入口，访问该文件收集相关依赖构成依赖树，默认为src/index.js。

**2、出口：output**

输出目录，可指定文件名和所在文件夹，会将模块打包到该目录下，一般为dist。

**3、loader**

webpack本身只能识别js和json文件，loader可以让webpack拥有处理其他文件的能力，常用的loader有css-loader、scss-loader、style-loader、babel-loader等。在module.rules里面进行配置：

```js
module.export = {
    module: {
        rules: [
            { text: /\.css$/, use: 'css-loader' },
            { text: /\.ts$/, use: 'ts-loader' }
        ]
    }
}
```

**4、插件：plugins**

loader让webpack可以处理其他类型文件，而插件使得webpack拥有更强大的能力，比如文件自动生成，打包优化，注入环境变量等。在plugins里面进行配置：

```js
const HtmlWebpackPlugin = require('html-webpack-plugin')
module.exports = {
    plugins: [new HemlWebpackPlugin({ template: './src/index.html' })]
}
```

**5、模式：mode**

环境，可以针对不同环境做相应的优化操作，有三种模式：development，production，none。