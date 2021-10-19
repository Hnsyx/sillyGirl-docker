# sillyGirl 傻妞

<a href="https://github.com/WindFgg/sillyGirl-docker"><img src="https://img.shields.io/github/stars/WindFgg/sillyGirl-docker.svg?style=popout-square" alt="GitHub stars"></a>
<a href="https://hub.docker.com/r/ranqi03/sillygirl"><img src="https://img.shields.io/docker/pulls/ranqi03/sillygirl?style=popout-square" alt="Docker Pulls"></a>
<a href="https://hub.docker.com/r/ranqi03/sillygirl"><img src="https://img.shields.io/docker/image-size/ranqi03/sillygirl?style=popout-square" alt="Docker Size"></a>
<a href="https://hub.docker.com/r/ranqi03/sillygirl"><img src="https://img.shields.io/docker/stars/ranqi03/sillygirl?style=popout-square" alt="Docker Stars"></a>

[sillyGirl 傻妞 项目地址](https://github.com/cdle/sillyGirl)     
[sillyGirl 傻妞 环境变量](https://github.com/cdle/sillyGirl#readme)   

镜像更新会在TG频道通知 建议关注频道

傻妞使用纯净版ubuntu制作 傻妞自带更新 因此不需要频繁更新docker镜像

[Github说明文档](https://github.com/WindFgg/sillyGirl-docker)

[TG 频道](https://t.me/kingfeng)   

[TG 群组](https://t.me/joinchat/XV2AZcvzFIUxNjI9)

## 使用说明
拉取镜像
 `docker pull  ranqi03/sillygirl`

运行镜像
``` bash
#精简版配置
docker run -dit \
   -v $PWD/sillyGirl/develop/:/sillyGirl/develop/ \
   -v $PWD/sillyGirl/conf/:/sillyGirl/conf/ \
   -v $PWD/sillyGirl/:/etc/sillyGirl \
   --name sillyGirl \
ranqi03/sillygirl:latest

#完整映射
docker run -dit \
   -v $PWD/sillyGirl/conf/:/sillyGirl/conf/ \
   -v $PWD/sillyGirl/develop/:/sillyGirl/develop/ \
   -v $PWD/sillyGirl/logs/:/sillyGirl/logs/ \
   -v $PWD/sillyGirl/:/etc/sillyGirl \
   --name sillyGirl \
ranqi03/sillygirl:latest
```
进入容器
`docker exec -it sillyGirl bash`

运行傻妞
``` bash
cd sillyGirl
git pull
source /etc/profile
go env
go build
./sillyGirl 

# QQ二维码出现后用小号扫码登录 之后用手机小号的QQ向自己的小号发送set qq matsers 主人QQ
# 开启傻妞自动升级是否通知 用主人QQ发送给机器人QQ set sillyGirl update_notify true
# 是否开启傻妞自动更新 用主人QQ发送给机器人QQ set sillyGirl auto_update true

./sillyGirl -d  #后台运行代码
```

重启容器
`docker restart sillyGirl`

停止并删除容器
```
docker stop sillyGirl
docker rm sillyGirl 
```

删除镜像
```
docker rmi ranqi03/sillygirl 
```

