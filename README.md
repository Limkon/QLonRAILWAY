# >**目前在CodeSandBox平台已经有更成熟的部署方案，此仓库已经弃用。**

>好用的话，可以给我点一下star吗，谢谢！

# 使用方法（Railway）
## 第一步：Fork本仓库

点击右上角的Fork按钮，将本仓库Fork到你自己的Github账户中。

## 第二步：新建railway项目

在[Railway](https://railway.app/dashboard)用相同的Github账号登录，点击New Project，新建一个项目。选择“Deploy from GitHub repo”，选择你Fork的这个仓库。

## 第三步：添加环境变量

**不要**选择“Deploy Now”，选择“Add variables”。

![添加环境变量](/pic/variables.png)

如图添加环境变量`PORT=5700`

![添加如图所示的环境变量](/pic/variables2.png)

## 第四步：获取访问域名

在Settings中找到Generate Domain按钮，点一下，获取访问域名。当然你也可以绑定你自己的域名。

![获取域名](/pic/Domain.png)

## 注意
>Railway平台的免费额度标准一直在变动，目前，Railway不用信用卡认证的免费额度是2刀+200小时/月，挂青龙面板并不现实。信用卡验证之后的免费额度为5刀+不限时/月，具体够不够挂青龙我也没有计算，这里仅仅是对在Railway上部署青龙面板的一个尝试。请自行辨别。
>
>2023年5月11日补充：经测试，拉了几个库一起跑，443个任务，一个号，预计月扣费4.61刀，刚好在5刀以内。
>
>![estimated](/pic/railway_estimated.png)

# 使用方法（Render）

类似的，你还可以在[Render](https://dashboard.render.com/)上使用本repository。

不同的地方仅仅在于，Render中新建的是Web Service。

![Web Service](/pic/webservice.png)

环境变量添加的地方变成了Environment选项卡。

![环境变量](/pic/environment1.png)

如下图所示添加环境变量即可。

![环境变量](/pic/environment2.png)

而且Render不需要你主动generate域名，他会自动生成域名，当然你也可以绑定自己的域名。

## 注意
>Render的每月免费额度高达750小时，足够覆盖单个项目的整月使用。但是由于Render的特性，容器每隔一段时间会强制重启，且删除所有数据，如果需要使用Render部署青龙，需要在Dockerfile中使用`ADD`命令将数据在构筑时添加进去，类似于[xiaoya_alist_docker_on_render](https://github.com/k0baya/xiaoya_alist_docker_on_render/blob/main/Dockerfile)的方法，在仓库中新建一个data文件夹并把数据都存入，在Render构筑时又能将数据复制进去。如果这么使用，请不要直接Fork，务必自建私密仓库后Import本仓库再上传data以保证数据安全。

# 容器保活

这些平台上托管的项目并不一定会一直保持活跃，有些在一段时间无人访问之后就会休眠，所以可以使用一些外部监控手段保活。

我已知的网站监控：
>1 [cron-job.org](https://console.cron-job.org)
>
>2 [UptimeRobot](https://uptimerobot.com/)

可供自行搭建的网站监控：
>[Uptime-Kuma](https://github.com/louislam/uptime-kuma)
>
>NodeJs
https-proxy-agent
ws
qrcode-terminal
tunnel
download
request
md5
got
ds
axios@0.27.2
crypto-js
prettytable
jsdom
date-fns
tough-cookie
tslib
ws@7.4.3
ts-md5
jsdom -g
jieba
fs
form-data
json5
png-js
global-agent
@types/node
require
typescript
js-base64
moment
axios
js-base64
dotenv
tough-cookie
ws@7.4.3
require
requests
date-fns
ts-md5
typescript
json5
axios@v0.27.2
crypto-js
@types/node
png-js
node-telegram-bot-api
fs
jsdom
form-data
jieba
tslib
ds
jsdom -g
prettytable
ql
common
node-jsencrypt
juejin-helper
moment
global-agent
cheerio
wget
redis

Python3
pycryptodome
Crypto
requests
pycryptodome
bs4
PyExecJS
aiohttp
canvas
ping3
jieba
jieba
PyExecJS
ping3
canvas
Crypto
ds
requests

Linux
--no-cache
python3-dev
libc-dev
npm
libc-dev
gcc

开卡变量填写，加在配置文件最后面

## 开卡系列通用变量 设置一次永久生效
export RUSH="true"
export guaopenwait_All="60"
export guaopencard_All="true"
export guaopencard_addSku_All="true"
export guaopencardRun_All="true"
export guaopencard_draw="true"
export guaunknownTask_addSku_All="true"
## 开卡系列抽奖通用变量 设置一次永久生效
export gua_carnivalcity_draw="true"
3.定时规则
*/5 * * * * ?    #每隔 5 秒执行一次
0 */1 * * * ?    #每隔 1 分钟执行一次
0 0 2 1 * ? *    #每月 1 日的凌晨 2 点执行一次
0 15 10 ? *    #MON-FRI 周一到周五每天上午 10：15 执行
0 15 10 ? 6L    #2002-2006 2002 年至 2006 年的每个月的最后一个星期五上午 10:15 执行
0 0 23 * * ?    #每天 23 点执行一次
0 0 1 * * ?    #每天凌晨 1 点执行一次
0 0 1 1 * ?     #每月 1 日凌晨 1 点执行一次
0 0 23 L * ?    #每月最后一天 23 点执行一次
0 0 1 ? * L    #每周星期天凌晨 1 点执行一次
0 26,29,33 * * * ?    #在 26 分、29 分、33 分执行一次
0 0 0,13,18,21 * * ?    #每天的 0 点、13 点、18 点、21 点都执行一次
0 0 10,14,16 * * ?    #每天上午 10 点，下午 2 点，4 点执行一次
0 0/30 9-17 * * ?    #朝九晚五工作时间内每半小时执行一次
0 0 12 ? * WED    #每个星期三中午 12 点执行一次
0 0 12 * * ?    #每天中午 12 点触发
0 15 10 ? * *    #每天上午 10:15 触发
0 15 10 * * ?    #每天上午 10:15 触发
0 15 10 * * ? *    #每天上午 10:15 触发
0 15 10 * * ?    #2005 2005 年的每天上午 10:15 触发
0 * 14 * * ?    #每天下午 2 点到 2:59 期间的每 1 分钟触发
0 0/5 14 * * ?    #每天下午 2 点到 2:55 期间的每 5 分钟触发
0 0/5 14,18 * * ?    #每天下午 2 点到 2:55 期间和下午 6 点到 6:55 期间的每 5 分钟触发
0 0-5 14 * * ?    #每天下午 2 点到 2:05 期间的每 1 分钟触发
0 10,44 14 ? 3 WED    #每年三月的星期三的下午 2:10 和 2:44 触发
0 15 10 ? * MON-FRI    #周一至周五的上午 10:15 触发
0 15 10 15 * ?    #每月 15 日上午 10:15 触发
0 15 10 L * ?    #每月最后一日的上午 10:15 触发
0 15 10 ? * 6L    #每月的最后一个星期五上午 10:15 触发
0 15 10 ? * 6L    #2002-2005 2002 年至 2005 年的每月的最后一个星期五上午 10:15 触发
0 15 10 ? * 6#3    #每月的第三个星期五上午 10:15 触发
四、常用命令
1.查看容器名
docker ps -a
2.重启青龙容器
docker restart 你的容器名
3.更新青龙（或者直接面板更新）
docker exec -it qinglong ql update
4.更新青龙并编译
docker exec -it qinglong ql restart
5.拉取自定义仓库，已Faker仓库为例
docker exec -it qinglong ql repo https://ghproxy.com/https://github.com/shufflewzc/faker2.git "jd_|jx_|gua_|jddj_|getJDCookie" "activity|backUp" "^jd[^_]|USER|ZooFaker_Necklace.js|JDJRValidator_Pure|sign_graphics_validate"
6.拉取单个脚本，以Faker库的资产变更通知为例
docker exec -it qinglong ql raw https://github.com/shufflewzc/faker2/blob/main/jd_bean_change_new.js
7.导出互助码
docker exec -it qinglong ql code
8.通知测试
docker exec -it qinglong notify test test
9.立即执行脚本，以资产变更通知为例
docker exec -it qinglong task jd_bean_change_new.js now
10.并行执行脚本
docker exec -it qinglong task jd_bean_change_new.js conc
11.查看青龙密码 注意你的容器及文件夹名称
docker exec -it qinglong cat /ql/config/auth.json
12.删除7天前的所有日志
docker exec -it qinglong ql rmlog 7
13.启动青龙bot 前提你已配置好青龙BOT
docker exec -it qinglong ql bot
g++
libffi-dev
python3-dev
gcc


