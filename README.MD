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

注意：一般我们会将App依赖的本地module集中在一个scope（文件夹）下，这样方便管理，也方便在.gitignore中统一排除, 而npm规定，scope的命名必须是一个这样的格式：
@scope-name/module-name,然后在.gitignore文件中我们一般会这样配置：
```
node_modules/*
!node_modules/@app/

```

将会link install module @app/module-a 到当前package。接下来你就可以像平常一样引用该 module。
```
import Cal from '@app/module-a'
```

## 运行本例
```
npm run go
```
