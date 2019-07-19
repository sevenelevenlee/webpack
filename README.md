# webpack
##安装
```
//全局安装
npm install -g webpack
//安装到你的项目目录
npm install --save-dev webpack
```

##使用npm执行和构建本地服务器
```
npm install --save-dev webpack-dev-server
在webpack配置中
 devServer: {
    contentBase: "./public",//本地服务器所加载的页面所在的目录
    historyApiFallback: true,//不跳转
    inline: true//实时刷新
  } 
 
 在package.json中添加
 "scripts": {
    "server": "webpack-dev-server --open"
  },

```
##配置不同的loader

```
npm install --save-dev babel-core babel-loader babel-preset-env babel-preset-react
npm install --save-dev style-loader css-loader

在webpack中配置
    module: {
        rules: [
            {
                test: /(\.jsx|\.js)$/,
                use: {
                    loader: "babel-loader"
                },
                exclude: /node_modules/
            },
            {
                test: /\.css$/,
                use: [
                    {
                        loader: "style-loader"
                    }, {
                        loader: "css-loader"
                    }
                ]
            }
        ]
    }

```
##关于倒入
              
