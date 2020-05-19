## k8s 部署
```
$ git clone --depth=1 https://github.com/SuperLandy/jumpserver-k8s
$ kubectl create ns jumpserver && kubectl apply -f ./k8s
$ kubectl get pod -n jumpserver
```

## k8s 说明

- k8s集群内需要有ingress和hpa组件
- 存储使用nfs，具体行为在nfs-pv.yml中定义，用户可根据实际情况进行修改
- koko和gua以及mysql密码等信息，可自行将其加密存放到k8s集群
- yml使用官方镜像，如自行打包的需修改k8s目录下yml文件中的image
- mysql使用endpoint提供，mysql_host信息在k8s/mysql-endpoint.yml中定义



## docker-compose 部署

```
$ git clone https://github.com/jumpserver/Dockerfile.git
$ cd Dockerfile
$ cat .env
$ docker-compose up
```

build
```
$ cd Dockerfile
$ cat .env
$ docker-compose -f docker-compose-build.yml up
```
## docker-compose 说明

- .env 的变量 用在 docker-compose 里面, 可以自己看下
可能还有一些未能检测到的问题, 尽量自己调试一遍后再使用

> 如果自己编译, 可以在 docker-compose 的 environment: 处加入 Version: $Version , 取代 Dockerfile 的 ARG




