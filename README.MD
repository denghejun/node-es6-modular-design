##  node-es-module-loader
nodejs 目前不能直接run es6的脚本。可以安装以下package快速的进行es6项目的开发：

```
npm install -g node-es-module-loader
```
接下来就可以用以下命令来run任何es6脚本

```
node-esml index.js
```
## npm link
npm link 常用来创建App内部的node package。避免在引用是出现超长度的import path。比如，本例中：
```
cd momdule_A && npm link
```
将会把 momdule_A 下的package打包成一个全局的node_module. 其package name 为momdule_A/package.json中的name。
并且该module源码的所有改动都会同步到全局。
```
cd ../ && npm link @app/module-a
```
将会link install module @app/module-a 到当前package。接下来你就可以像平常一样引用该 module。
```
import Cal from '@app/module-a'
```

## 运行本例
```
npm run go
```
