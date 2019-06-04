# sspanel v3 mod 配置

## 前端配置

## 后端配置

### 通过docker

#### 环境变量

```dockerfile
NODE_ID=0                     
SPEEDTEST=6                   
CLOUDSAFE=0                   
AUTOEXEC=0                    
ANTISSATTACK=0                
MU_SUFFIX=zhaoj.in            
MU_REGEX=%5m%id.%suffix       
API_INTERFACE=modwebapi       
WEBAPI_URL=https://zhaoj.in   
WEBAPI_TOKEN=glzjin           
MYSQL_HOST=127.0.0.1          
MYSQL_PORT=3306               
MYSQL_USER=ss                 
MYSQL_PASS=ss                 
MYSQL_DB=shadowsocks          
REDIRECT=github.com           
FAST_OPEN=fals
```

#### 普通配置:

安装docker

```
docker version > /dev/null || curl -fsSL get.docker.com | bash
service docker restart
```

**webapi** 方式对接:

```
docker run -d --name=ssrmu -e NODE_ID=节点ID -e API_INTERFACE=modwebapi -e WEBAPI_URL=需要对接的地址 -e WEBAPI_TOKEN=前端设置的token --network=host --log-opt max-size=50m --log-opt max-file=3 --restart=always fanvinga/docker-ssrmu
```

**数据库**方式对接：

```
docker run -d --name=ssrmu -e NODE_ID=节点ID -e API_INTERFACE=glzjinmod -e MYSQL_HOST=MYSQL地址 -e MYSQL_USER=mysql用户名 -e MYSQL_DB=数据库名 -e MYSQL_PASS=数据库密码 --network=host --log-opt max-size=50m --log-opt max-file=3 --restart=always fanvinga/docker-ssrmu
```

#### docker 常用命令

```
docker container ls
#查看所有正在运行的 docker 
docker logs -f dockername
#查看选定 docker 的 log
docker rm -f dockername
#删除指定 docker
docker system df
#查看容器使用的磁盘空间
docker system prune -a
#对 docker 进行全面垃圾回收
```

##### docker err

```
systemctl daemon-reload

systemctl restart docker.service
```





### 普通配置一键命令

#### For centos7 x64

```
yum install wget -y && wget https://raw.githubusercontent.com/SuicidalCat/Airport-toolkit/master/ssr_node_c7.sh && chmod +x ssr_node_c7.sh && ./ssr_node_c7.sh
```

#### For ubuntu 18.04  x64

```
apt-get install wget -y && wget https://raw.githubusercontent.com/SuicidalCat/Airport-toolkit/master/ssr_node_u18.sh && chmod +x ssr_node_u18.sh && ./ssr_node_u18.sh
```



### 设置开机启动

```
systemctl enable ssr_node
```

### 服务启动

```
systemctl start ssr_node
```

### 服务停止

```
systemctl stop ssr_node
```