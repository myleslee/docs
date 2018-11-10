# Client Engine 快速入门 · Node.js

该文档帮助你快速了解如何创建一个 Client Engine 项目，该项目是一个简单的双人剪刀石头布游戏，游戏逻辑的开发依赖于实时对战 JavaScript SDK。

我们在这篇文档中先了解如何本地启动项目，简单试玩一下，然后部署项目到云端。之后在[开发指南](client-engine-guide-node.html)中会介绍详细的游戏逻辑以及如何开发自己的游戏。

## 启动项目

### 安装命令行工具
请查看命令行工具**[安装部分](leanengine_cli.html#安装)**的文档，安装命令行工具，并执行**[登录](leanengine_cli.html#登录)**命令登录。


### 创建项目
从 Github 迁出示例项目，请将该项目作为你的项目基础：

```js
git clone https://github.com/leancloud/client-engine-nodejs-getting-started
cd client-engine-nodejs-getting-started
```

添加应用 App ID 等信息到该项目：

```
lean switch
```

在第一步选择 App 中，选择您的游戏对应的 LeanCloud 应用。在第二步选择云引擎分组时，必须选择 `_client-engine` 分组，LeanCloud 仅对该分组提供专门针对 Client Engine 的优化维护及各种支持，如图所示：

![image](images/client-engine-lean-switch.png)


### 本地运行

首先在当前项目的目录下安装必要的依赖，执行如下命令行：

```
npm install
```

如果同时会使用到数据存储服务，执行如下命令：

```
npm install leancloud-storage
```

启动应用时打开调试日志：

```
DEBUG=ClientEngine*,RPS*,Play  lean up
```

如果您不需要调试日志，可以直接使用以下命令启动：

```
lean up
```

启动后在浏览器中打开 `http://localhost:3000/` ，检测项目是否正常启动。

### 访问站点

#### 感受游戏

服务端项目启动完成后，如果希望体验 Demo 游戏，需要额外同时打开两个[客户端示例 Demo](https://client-engine-app.leanapp.cn/)页面，在这两个页面中做如下配置：

点击 Configs，APP_ID 和 APP_KEY 填入之前选择的应用的 App ID 及 App Key：

```sh
# 如果您的浏览器已经登录 LeanCloud，请在下方选择相关应用，复制粘贴相关信息到 Configs 中：
 APP_ID:  "{{appid}}"
 APP_KEY: "{{appkey}}"
```

接着在 Client Engine Server 中输入 `http://localhost:3000`。如图所示：

![image](images/client-engine-browser-demo.png)

信息填写完成后，点击「Login to Play」就可以开始游戏了。

#### 客户端代码

如果您希望查看详细的客户端代码，可以访问位于 github 的[客户端示例代码](https://github.com/leancloud/client-engine-demo-webapp)。


## 部署到云端

在根目录中运行：

```
lean deploy
```

在浏览器中登录 LeanCloud 控制台，进入 Play - Client Engine - 设置，在「Web 主机域名」中设置二级域名，通过 `http://stg-<YOUR-APP-DOMAIN>.leanapp.cn` 访问预备环境。

例如填写 `myapp`，设置成功后通过 `http://stg-myapp.leanapp.cn`访问，此时可以看到 Client Engine 服务端正在运行的文本。

其他详细的部署方式请参考命令行工具文档中的[部署](leanengine_cli.html#部署)及[发布到生产环境](leanengine_cli.html#发布到生产环境)。

## 开发指南
该初始项目已经帮您写好了通用的游戏逻辑，并提供了便利的方法及属性，因此我们推荐您在该项目的基础上开发自己的游戏逻辑。
进一步了解如何使用该项目请参考 [Client Engine 开发指南 · Node.js](client-engine-guide-node.html)。
