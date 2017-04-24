### 前言

`TypeScript` 相对于传统 `JavaScript`，在类型方面进行了增强，以实现诸如`类型检查`、`语法提示`等等功能。在 `ypeScript` 中使用传统 `JavaScript` 库，如` angularjs jQuery` 等，需要为其引入对应类型定义文件。关于类型定义文件的管理工具，经历了 `tsd、typings` 两代进化，现在官方推荐的方式是使用` npm` 进行管理。

### 安装TypeScript编译工具
安装好`Node.js后`，打开cmd窗口，输入以下命令

    $ npm install -g typescript
    
使用npm包管理工具下载`TypeScript`包并在全局环境下安装，安装成功后就可以通过` tsc` 命令编译TypeScript源码。

可以通过 `tsc -v `命令查看当前`TypeScript版`本。

### 类型定义库

Github 上的开源项目 [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) 用于维护常见 JavaScript 库的类型定义。

通过 [TypeSearch](https://microsoft.github.io/TypeSearch/) 搜索对应库的类型定义文件。

### 安装类型定义文件

以 `angularjs` 为例，在工程根目录下执行如下命令以安装类型定义文件

    $ npm install @types/angular --save-dev
对应的类型定义文件将被安装在 工程根目录/node_modules/@types 目录下。

### 配置 tsconfig.json

工程根目录/src 下的 `tsconfig.json` 用于配置 TypeScript 编译选项。在使用 npm 进行类型定义文件管理时，它的配置如下

```javascript
{
    "compilerOptions": {
        "module": "commonjs",
        "target": "ES5",
        "noImplicitAny": true,
        "removeComments": true,
        "preserveConstEnums": true,
        "sourceMap": true,
        "rootDir": "./",
        "outDir": "../www"
    },
    "exclude": [
        "bower_components",
        "components",
        "../www"
    ],
    "include": [
        "../node_modules/@types",
        "./"
    ]
}
```
在未配置 typeroots 的前提下，TypeScript 编译器会自动寻找引入 `node_modules/@types` 目录中的类型定义文件。更多信息请参考 [tsconfig-json types typeroots and types](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#types-typeroots-and-types)

### 升级 TypeScript

* $ npm uninstall -g typescript

* $ npm install -g typescript

* $ tsc -v
* 确认版本号在 2.0 以上

* 升级 Netbeans TypeScript Editor 插件

* 匹配 TypeScript 2，Netbeans 插件也需升级。在 nbts 下载最新的 [.nbm](https://github.com/Everlaw/nbts/releases) 插件并导入 Netbeans 即可。

### Reference

* [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) 
* [tsconfig-json types typeroots and types](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#types-typeroots-and-types) 
* [nbts](https://github.com/Everlaw/nbts/releases)
