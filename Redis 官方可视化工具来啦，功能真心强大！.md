# Redis 官方可视化工具来啦，功能真心强大！

Python开发者 *2022-03-14 08:30*

以下文章来源于macrozheng ，作者梦想de星空

[

![](http://wx.qlogo.cn/mmhead/Q3auHgzwzM6oiccxQhwhZWiazE7gqJOg1LLAEXmWYTqEkRsAmDPKnMdg/0)

**macrozheng**.

专注Java技术分享，涵盖SpringBoot、SpringCloud、Docker、中间件等实用技术，作者Github开源项目mall（50K+Star）。

](https://mp.weixin.qq.com/s/1GxWMsK12rIa_be31VM7yg#)

> 最近逛了一下Redis官方网站，发现Redis不仅推出了很多新特性，而且还发布了一款可视化工具`RedisInsight`。试用了一下感觉非常不错，最关键的是能支持RedisJSON之类的新特性，这是第三方工具无法比拟的。今天带大家体验一下`RedisInsight`，确实非常好用！

## **RedisInsight简介**

RedisInsight是Redis官方出品的可视化管理工具，可用于设计、开发、优化你的Redis应用。支持深色和浅色两种主题，界面非常炫酷！可支持String、Hash、Set、List、JSON等多种数据类型的管理，同时支持远程使用CLI功能，功能非常强大！

下面是RedisInsight的一张使用效果图，颜值不错！

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxONxPiazNVpZQwY0PpthNibPXoJff8oib5BBjJC5O7LQN26nDtXfqQhVicg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

## **RedisMod简介**

Redis经过多年发展，早已不仅仅是一个内存数据库了。有了RedisMod的支持，Redis的功能将变得非常强大。RedisMod中包含了如下增强模块：

- RediSearch：一个功能齐全的搜索引擎；

- RedisJSON：对JSON类型的原生支持；

- RedisTimeSeries：时序数据库支持；

- RedisGraph：图数据库支持；

- RedisBloom：概率性数据的原生支持；

- RedisGears：可编程的数据处理；

- RedisAI：机器学习的实时模型管理和部署。

## **安装**

> 首先我们将使用Docker来安装Redis，注意下载Redis的完全体版本RedisMod，它是内置了所有模块的增强版Redis！

- 使用如下命令下载RedisMod的镜像；

`docker pull redislabs/redismod:preview`

- 在容器中运行RedisMod服务。

```
docker run -p 6379:6379 --name redismod \  
-v /mydata/redismod/data:/data \  
-d redislabs/redismod:preview
```

## **使用**

> Redis服务安装完毕，接下来我们就使用RedisInsight来管理下它试试！

### 基本使用

- 首先下载RedisInsight的安装包，下载地址：https://redis.com/redis-enterprise/redis-insight/

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxmQXj5l9FKSibAZ6svdF7icHmcHfqEYaias2B62PAurPF83D4mpw4rRwicQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 下载完成后直接安装即可，安装完成后在主界面选择`添加Redis数据库`；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxqS2PFVVicwSMUib9JG3A461AQscjib3PSu0keAnWPibURicic3iaLTIzeXowQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 选择`手动添加数据库`，输入Redis服务连接信息即可；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxM686MAuYXUVpiaUEiamiaSyb9AZg7fFIyhgbiaxADsSeEpiaVp10xcMK0Og/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 打开连接后即可管理Redis，右上角会显示已经安装的Redis增强模块；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxTdIyfLM2Xb0YI6aCMiaXqYcONfGKloIlZKIpXcxzEyBjTkIicDruRB5Q/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 接下来我们就可以通过RedisInsight在Redis中添加键值对数据了，比如添加`String`类型键值对；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxshw1jibphPDrRibWR9ICN7a0gwW8iaUNqPndSHAOCibNDaypasuJabMqlA/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 添加Hash类型，编辑的时候可以单个属性编辑，还是挺方便的；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMx35OYibniawGVGqJGzCsNXbDRF7wWXXhWvMu3ydFQWckNjiaQ6ZWYy6orw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 添加List类型，编辑的时候可以直接Push元素进去；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxRdBEWmficDceYxBy2EoMCUaKsDGQH9TVXdNQcSKgIwlYk9aroBtRxUg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 添加JSON类型，安装RedisJSON模块后可支持；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxL7m0YnSVFVN2FeoUfH4y1GZQZ4S9t1cppAjjurFsS3cTogxnfib0WDw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 对原生JSON类型，不仅支持高亮预览，还能支持新增、编辑和删除单个属性，够方便！

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxGicscWcibm8xotquVTGEhOyVZGHRAoAtktJsYxsLSgTDRWjuVqXnSSlQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 另外RedisInsight还支持深色和浅色两种主题切换，在设置中即可更改。

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxDG4THJKoY2qec5jxj2l6TNtupscAictV2QWDrqrtZVt5yP1qagND6cQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

### CLI

- 如果RedisInsight的图形化界面功能满足不了你的话，还可以试试它的`CLI`功能，点击左下角CLI标签即可打开；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxWXLX1kTYktynlqnArMic9w6ILH6XjZOwozFN0d8MicRsuiaUYK4WgiaB4g/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 贴心的Redis官方怕你记不住命令，还添加了`Command Helper`这个查找命令文档的功能，比如我们可以搜索下`hget`这个命令的用法。

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxbz97adFghLkInAOJ7aftINhnpcycMqriawzNwWcuO2xwYRglPmHy6Zg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

### Profiler

通过Profiler功能，我们可以查看Redis的命令执行日志，比如我们使用RedisInsight添加一个叫`testKey`的键值对，Profiler将显示如下日志。

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxJjuJDkne1S2jib9qoVfMcJctt0fcbneYEU2lrhPKFHBQuSYdtMdsDxQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

## **可视化监控**

> RedisInsight的Redis监控功能比较简单，个人比较喜欢使用Grafana来监控Redis，Grafana的具体使用可以参考Grafana使用教程 。

## 

## **安装Grafana**

- 首先下载Grafana的Docker镜像；

`docker pull grafana/grafana`

- 下载完成后运行Grafana；

```
docker run -p 3000:3000 --name grafana \  
-d grafana/grafana
```

- 接下来下载Prometheus的Docker镜像；

`docker pull prom/prometheus`

- 在`/mydata/prometheus/`目录下创建Prometheus的配置文件`prometheus.yml`：

```
global:  
  scrape_interval: 5s
```

- 运行Prometheus，把宿主机中的配置文件`prometheus.yml`挂载到容器中去；

```
docker run -p 9090:9090 --name prometheus \  
-v /mydata/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \  
-d prom/prometheus
```

- 进入grafana容器并安装`redis-datasource`插件，安装完成后需要重启grafana服务。

```
docker exec -it grafana /bin/bash  
grafana-cli plugins install redis-datasource
```

### 使用

- 连接到redismod需要使用到它的容器IP地址，使用如下命令查看redismod容器的IP地址；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxoy96d6ljajuXskk0YDHeyKBq0qeFRQUG5icD8shacfa4YKrqrribX7nQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 在Grafana中配置好Redis数据源，使用`admin:admin`账户登录，访问地址；http://192.168.3.105:3000/

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxzBqs2TJiaoMtZM028gibAz1trRT2aw4tovB2xCovTMwQ0ulibm64WGsxw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 配置Redis地址信息，注意使用redismod的容器IP地址；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxqqJTzNmrCaXuTmyRQxwFE0xwppoibeNobcQ1gQdVEPt3u1TaTlrFMPg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 打开Dashboard选择Redis；

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxFV0HUeMcVgial4YNvonEcydpqaO6PuL0Drb0ZkHTvJibK0Rnfr62Qxkw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 接下来就可以看到一个非常完善的Redis监控仪表盘了，基本能满足Redis的监控需求。

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMx0V7BjO34VZvZpf4ax89cIyBWlsc1LmLZ3hkHGMuFsHQfdNJlCg98pw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

## **总结**

RedisInsight不愧是官方出品的可视化工具，感觉是目前用起来体验最好的Redis工具了！特别是对Redis新特性的支持，其他工具是无法比拟的！不过对Redis的监控功能确实有点简单，还是得用专业的监控工具Grafana来监控Redis！

## **参考资料**

> 感觉Redis的官方文档做的特别良心，强烈建议大家看下！

![图片](https://mmbiz.qpic.cn/mmbiz_png/CKvMdchsUwnP8pq58EOF6FXibUVy19icMxgiaAh4ghXe78gZ8wQMfFqWicCkSgp3pEvPwWHbqsdGYNNdE2ADniaxibNw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

官方文档：https://developer.redis.com/explore/redisinsightv2

- EOF -