# radxa-docs

本文档平台基于 [Docusaurus 2](https://v2.docusaurus.io/)构建的文档平台，关于 Docusaurus 的使用方法请参考官方网站 [Docusaurus 2](https://v2.docusaurus.io/)。

## 使用方法

首先克隆仓库代码：

```bash
# $ git clone http://192.168.2.13/W/radxa-docs.git
  git clone https://github.com/Keoy823/radxa-docs.git

```

安装依赖：

```bash
$ yarn install
# 或使用 npm install，下同
```

启动项目：

```bash
$ yarn start
```

构建项目：

```bash
# 同时构建中文和英文版 
$ yarn build
```

## 目录介绍

下面是主要目录的介绍：

```bash
├── docs                          
│   └── doc1.md                    # 文档          
├── docusaurus.config.js
├── package.json
├── sidebars.js                    
├── src
│   ├── components                 # 自定义组件
│   ├── css                        # 自定义 CSS
│   ├── pages                      # 自定义页面
├── static
│   ├── icons                      # 公用图标
│   ├── img 
└── yarn.lock                      
```