<!--
 * @Author: be_loving@163.com 
 * @Date: 2024-12-26 11:24:03
 * @LastEditors: be_loving@163.com 
 * @LastEditTime: 2024-12-26 11:29:13
 * @FilePath: /dolphinscheduler/README.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->

# 本库用于快速部署Apache Dolphinscheduler

相比拉取源代码库，本库只需要必要的yml和env文件即可，同时，文件夹的名称会成为docker容器分组的名称，直接用dolphinscheduler更容易分辨。

## 设置docker mirrors:
其中的镜像地址可能会失效，也存在不稳定的情况，如果失败可重试，多次失败的话请尝试其他的镜像地址，一定要搜比较新的，镜像地址失效的链接很多。

``` docker-config

{
  "builder": {
    "gc": {
      "defaultKeepStorage": "20GB",
      "enabled": true
    }
  },
  "experimental": false,
  "registry-mirrors": [
    "https://dockerpull.org"
  ]
}
```


## 第一次运行，初始化数据库等
docker-compose --profile schema up -d 


## 启动所有服务
docker-compose --profile all up -d