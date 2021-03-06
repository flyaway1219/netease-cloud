# 常见问题 {docsify-ignore-all}

### 1. 确保自己的账号密码都没有问题，却总是提示检查账号密码怎么回事？

答：很有可能是当前的API不可用了，默认API使用的人较多，，而且大多都挤在一个时间段用了，，导致平台反应不过来，本身就是国外站，速度比较慢，大家可以分开点做任务，下午晚上都是可以的，不然这个API就会被挤挂掉了，还是建议大家自己搭建API，这样自己访问速度也会快很多。
大家部署完API记得在 **init.config**文件中更改 **api**地址为自己部署的地址，比如你的域名是api.test.com或者api.glitch.me等等。



### 2. 已经换了API，还是报错检查账号密码？

答：如果确定API可以用，但依旧提示账号密码有问题，还请检查一下配置文件的账号密码以及**md5Switch**有没有选对，密码的MD5一定要是**32位小写**，已经有人因为没注意这个而出错的了。

并且 **init.config**文件中要更改 **api**地址为自己部署的地址。



### 3. 打卡完成后为什么歌曲累计播放没有涨或者涨幅很小？

答：打卡完成后听歌数量并不会立刻更新，建议等待半小时或者更多一段时间，由于官方计数规则限制，只有从未听过的歌曲才计入总数，所以如果你的播放量本来就很高，建议加大打卡的循环次数，教程见其他事项第三条。



### 4. 自己用服务器搭建的API，首页能打开，但点击检查没反应？

答：API一定要用PHP部署，如果是纯静态是没有任何作用的，建议新手或者小白使用前两种部署方式，有能力者使用第三种。

### 5. 使用多账号报错怎么办？

答：在确保其他配置没有问题的情况下，检查一下`account.json`里面的格式是否正确，账号与账号之间要有逗号，具体格式参考项目里的案例。

### 6. 使用这个会影响我的听歌风格吗？

答：刷的歌都来自您的每日推荐歌单，不影响。

### 7. 使用这个我的账号安全吗？

答：从技术上来说，在配置文件中填写的账号密码无论是自行加密还是让程序加密（MD5其实不是加密，只是一种摘要算法，用来防止文件信息等被篡改），最终API接口收到的都是MD5，假设你使用的是网上随便找的API，即使别人改过代码，保存了你的账号信息，想要通过彩虹表暴力破解，也是大费周章还只能搞到简单的密码，至于大神级别的Hack可能毫无压力，但人家大神也不稀罕做这些，所以说安全性基本上没有问题。

### 8. 其他报错

##### 错误：{"errorCode":1,"errorMessage":"user code exception caught","stackTrace":"module 'index' has no attribute 'main_handler'"}

答：这个是通过云函数部署报的错，原因是没有改执行方法，请看云函数部署那一节的图片内容。

##### 错误：在您选择的文件夹里面找不到netease-cloud-master/index.py文件

答：重新去GitHub下载最新的项目。

##### 错误：腾讯云提示当前函数状态不支持绑定触发器怎么办?

答：新用户初次使用需要对角色授权，允许服务代替用户完成对授权资源的操作。操作步骤见官网文档。

还有其他问题可以提Issue，遇到程序报错可以截图或者复制报错信息。