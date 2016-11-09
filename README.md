#项目搭建
环境node npm
-
build命令也改了：npm run dist
##YEOMAN
1. npm install -g yo
2. 在generators中寻找react-webpack
3. 安装npm install npm install -g generator-react-webpack
    1. 过程中选择SASS
    2. postcss选择yes(用postcss就不需要添加autoprefix-loader)
    3. 之后配置在css与sass中直接写入postcss-loader!就可以取代autoprefix-loader配置了
4. 切换项目文件夹，yo react-webpack 构建项目
5. npm run serve 或者npm start 热启动项目调试
6. 在main.js中编辑自己的主JS文件

##项目编写
1. 安装autoprefixer自动完成css样式的前缀，兼容浏览器
    npm install autoprefixer-loader --save-dev
2. 配置相关文件，在cfg中default.js中配置autoprefixer
3. autoprefixer配置文档https://github.com/passy/autoprefixer-loader

##配置JSON文件的加载
1. 先配置一个JSON文件
2. 然后安装解析JSON的包，npm install --save-dev  json-loader
3. 在cfg中default.js中配置JSON文件解析
    {
        test:/\.json$/,
        loader:'json-loader'
     }
4. 在main.js中引入JSON文件
    var json = require("json!./file.json");
5. 在main.js中将图片信息fileName转换成图片路径URL信息
    