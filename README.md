# 🦊 FoxONE-CLI
说三遍：

**node >= 10.13.0**

**node >= 10.13.0**

**node >= 10.13.0**

## 快速开始
- 常规初始化操作：
    ```shell
    npx @foxone/cli init
    ```

- 初始化项目但不安装依赖
    ```shell
    npx @foxone/cli init -n
    ```

- 初始化一个项目名为 *hp-hybrid* 的 **hybrid** 项目：
    ```shell
    npx @foxone/cli init -b hp-hybrid
    ```

- 要创建多个项目，把脚手架安装到全局：
    ```shell
    npm i -g @foxone/cli
    ```
  安装完成后执行初始化操作：
    ```shell
    fox init
    ```
---

## 项目类型简介
### SPA 应用
- [x] 基于 [Vue](https://vuejs.org/) 框架

- [x] 基于 [Vue-Router](https://router.vuejs.org/) 实现前端路由

- [x] 使用 [typescript](https://www.typescriptlang.org/) 进行开发

- [x] 集成 [debug 调试服务]()，项目启动后，输入 http://localhost:6200/debug 即可进入

- [x] 遵守 [eslint](https://eslint.org/) 规范

- [x] 遵守 [stylelint](https://stylelint.io/) 规范

- [x] 采用 [prettier](https://prettier.io/docs/en/install.html) 美化代码格式

- [x] 最佳实践的 [webpack](https://webpack.js.org/) 配置，默认实现诸如 *babel-import-plugin 按需加载*、*JS文件拆分*、*css、html文件压缩提取*、*文件大小分析*……，当然你可以在 `configs/webpack.config.*.js` 中自定义想要的任何配置

- [x] 无缝支持 rem 和 viewport 移动端布局，无需额外配置

---

## 插件列表

| 名称 | 阶段 | 功能 |
| --- | --- | --- |

---

## [fox.config.js 详解]()
- 在使用脚手架构建好一个项目后，会在项目根目录下生成一个 `fox.config.js` 的配置文件

- 你可以通过修改配置文件，对项目的 *开发环境*、*新建模板*、*打包编译*、*构建发布* 等各个阶段进行更为精确的控制

- [点击]() 查看配置表的详细阐述

---

## 脚手架使用命令
```shell
Usage: fox [command] [options]

Options:
  -v, --version           output the version number
  -h, --help              output usage information

Commands:
  init [options]          初始化项目
  dev [options]           fox dev -p [port]
  start [options]         fox start -p [port]
  new [options] <module>  fox new <module> [-f | -c]
  build [options]         根据 [fox.config.js] 构建你的项目
  release [options]       根据 [fox.config.js] 发布你的项目
```

### 初始化项目 - fox init
```shell
使用: fox init [options]

初始化项目

Options:
  -a, --spa [name]        创建一个单页应用项目(SPA)
  -n, --no-install        初始化项目不安装任何依赖
  -c, --config <path>     根据config文件进行项目初始化
  -P, --path <path>       创建项目的工作路径
  -h, --help          output usage information
```

### 启动开发服务 - fox dev
```shell
使用: fox dev [options]

fox dev [-p <port>] [-H <host>] [-P <path>]

Options:
  -p, --port <port>      根据指定的端口号启动开发服务
  -H, --hostname <host>  根据指定的hostname启动开发服务
  -P, --path <path>      启动开发服务的工作路径
  -h, --help         output usage information
```

### 启动生产服务 - fox start
```shell
使用: fox start [options]

fox start [-p <port>] [-H <host>] [-P <path>]

Options:
  -p, --port <port>      根据指定的端口号启动生产服务
  -H, --hostname <host>  根据指定的hostname启动生产服务
  -P, --path <path>      启动生产服务的工作路径
  -h, --help         output usage information
```

### 创建新模板 - fox new
```shell
使用: fox new [module] [options]

fox new [module] [-f | -c]

Arguments:

  module          组件名

Options:
  -f, --function      创建一个函数组件
  -c, --class         创建一个类组件
  -P, --path <path>   创建组件的工作路径
  -h, --help      output usage information
```

### 项目构建 - fox build
```shell
使用: fox build [options]

根据 [fox.config.js] 构建你的项目

Options:
  -c, --config <path>  手动指定构建配置文件路径
  -n, --no-verify      绕过所有的预检
  -s, --sourcemap      构建出sourcemap
  -P, --path <path>    构建的工作路径
  -h, --help           output usage information
```

### 项目发布 - fox release
```shell
使用: fox release [options]

根据 [fox.config.js] 发布你的项目

Options:
  -a, --automatic         自动迭代版本号
  -i, --ignore            忽略迭代版本号
  -m, --manual <version>  手动迭代版本号
  -t, --tag <tag>         发布时带上tag
  -n, --no-verify         绕过所有的预检
  -P, --path <path>       发布的工作路径
  -h, --help              output usage information
```