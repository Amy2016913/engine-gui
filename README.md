游戏引擎设计
# HOW TO
按照第一周的说明   
# 第一周 gui初步：electron配置&Hello world
## 安装electron
1. 更新npm
```
npm install npm -g
```
2. 更新Node：去官网下载最新node，安装即可
3. 安装electron：npm install electron -g   
如果安装成功，在命令行中输入electron会有窗口跳出   
## 安装依赖
```
npm install    
```
## 运行
```
tsc && electron .   
```
## 笔记
### electron
electron程序有main和render两个进程。进城之间不能随意通信。约定将它们放到两个文件夹里以便区分    
"主进程负责管理平台相关的调度，如窗口的开启关闭，菜单选项，基础对话框等等"    
"每一个新开启的窗口是一个独立的渲染进程"      
"简单点说，Electron 的主进程相当于一个 Node.js 服务端程序，而每一个窗口（渲染进程）则相当于一份客户端网页程序。" 
 Electron 提供了进程间通信对应的模块 ipcMain 和 ipcRenderer       
运行流程：package.json → index.js → 创建窗口（index.html）
### others
先把主要逻辑写出、写死，然后改    
require和import：后者才会有代码提示
## 遇到的问题
- engine怎么include都不成功，后来发现貌似因为outDir里的文件无法被include      
- 无法引用文件：在src/renderer中新建listview.ts，其中有class listview，在gui.ts中无法使用     