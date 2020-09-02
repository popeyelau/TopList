你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# 今日热榜

[![Build Status](https://travis-ci.com/async-rs/async-std.svg?branch=master)](https://github.com/tophubs/TopList/)
[![License](https://img.shields.io/badge/license-MIT%2FApache--2.0-blue.svg)](https://github.com/tophubs/TopList/)

**今日热榜是一个获取各大热门网站热门头条的聚合网站，使用Go语言编写，多协程异步快速抓取信息，预览:[https://www.printf520.com/hot.html][热榜]**
![DeepinScrot-4337.png](https://i.loli.net/2019/08/05/PjX2nqWAgM5xsL4.png)

### 安装教程


1. 执行database.sql创建数据库,并配置/Config/Mysql.go数据库连接地址
2. 部署定时任务/App/GetHot.go爬虫程序，且以守护进程的方式执行Server.go
3. 打开hot.html今日热榜页面


### 目录说明

```
TopList/
├── App
│   ├── GetHot.go   爬虫程序需要Cron定时任务执行
│   └── Server.go   Server程序需要守护进程的方式执行
├── Common
│   ├── Db.go       DB组件
│   └── Message.go  
├── Config
│   ├── MySql.go    mysql配置读取组件
│   └── mysql.toml  mysql配置文件需要手动配置
├── Cron
│   ├── GetHot.sh   爬虫Cron程序可以是每小时执行一次
│   └── README.md
├── database.sql    数据库建表文件
├── Html
│   ├── css
│   ├── hot.html    前端热榜展示网页
│   └── js
│  
└── README.md
```

### API说明

#### 获取所有类型
- Method: **GET**
- URL:  ```https://www.printf520.com:8080/GetType```
- Param：无
- Body:
```
{
    "Code":0,
    "Message":"获取数据成功",
    "Data":[
        {"id":"1","sort":"63908","title":"知乎"},
        {"id":"2","sort":"21912","title":"虎扑"},
        {"id":"6","sort":"11707","title":"天涯"},
        {"id":"7","sort":"12546","title":"知乎日报"},
       ]}
```


### 获取具体类型热榜数据
- Method: **GET**
- URL:  ```  https://www.printf520.com:8080/GetTypeInfo?id=2```
- Param：id
- Body:
```
{
    "Code":0,
    "Message":"获取成功",
    "Data":[
        {
            "title":"
45个经典面试回答提示，分享给即将工作的大家。 zt
",
            "url":"https://bbs.hupu.com//28814429.html"
        },
        {
            "title":"
[名场面]回家的诱惑：洪世贤酒店幽会，抵不住诱惑犯了错！ zt
",
            "url":"https://bbs.hupu.com//28818367.html"
        },
        {
            "title":"
张艺兴回应假唱风波。ZT
",
            "url":"https://bbs.hupu.com//28815609.html"
        }
    ]
}
```


### 使用说明

1. fork 项目

### 参与贡献

1. Fork 本项目
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


[热榜]: https://www.printf520.com/hot.html
