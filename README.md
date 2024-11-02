# CTFd-docker
可以快速使用Docker一键配置CTFd

此版本的CTFd集合Whale插件，用以部署动态容器挑战

[CTFd-docker配置参考](https://blog.hz2016.com/2022/03/%e3%80%90ctfd%e3%80%91%e9%9d%b6%e5%9c%ba%e5%ae%89%e8%a3%85%e4%b8%8e%e9%85%8d%e7%bd%ae%ef%bc%88docker%e4%b8%80%e9%94%ae%e9%85%8d%e7%bd%ae%e7%89%88%ef%bc%89/)

## 快速安装

在Ubuntu20.04、Ubuntu22.04、Kali 23.3、macOS 14.2+orbStack下完成过测试

你需要修改docker-compose.yml中的CTFD_URL、DIRECT_URL、DYNAMIC_URL，并在DNS服务器上做解析

>如果你要在本机进行测试，你可以使用如下host设置

<<<<<<< HEAD
```
127.0.0.1 ctfd.test.com
127.0.0.1 direct.test.com
127.0.0.1 dynamic.test.com
=======
## Install

1. Install dependencies: `pip install -r requirements.txt`
   1. You can also use the `prepare.sh` script to install system dependencies using apt.
2. Modify [CTFd/config.ini](https://github.com/CTFd/CTFd/blob/master/CTFd/config.ini) to your liking.
3. Use `python serve.py` or `flask run` in a terminal to drop into debug mode.

You can use the auto-generated Docker images with the following command:

`docker run -p 8000:8000 -it ctfd/ctfd`

Or you can use Docker Compose with the following command from the source repository:

`docker compose up`

Check out the [CTFd docs](https://docs.ctfd.io/) for [deployment options](https://docs.ctfd.io/docs/deployment/installation) and the [Getting Started](https://docs.ctfd.io/tutorials/getting-started/) guide

## Live Demo

https://demo.ctfd.io/

## Support

To get basic support, you can join the [MajorLeagueCyber Community](https://community.majorleaguecyber.org/): [![MajorLeagueCyber Discourse](https://img.shields.io/discourse/status?server=https%3A%2F%2Fcommunity.majorleaguecyber.org%2F)](https://community.majorleaguecyber.org/)

If you prefer commercial support or have a special project, feel free to [contact us](https://ctfd.io/contact/).

## Managed Hosting

Looking to use CTFd but don't want to deal with managing infrastructure? Check out [the CTFd website](https://ctfd.io/) for managed CTFd deployments.

## MajorLeagueCyber

CTFd is heavily integrated with [MajorLeagueCyber](https://majorleaguecyber.org/). MajorLeagueCyber (MLC) is a CTF stats tracker that provides event scheduling, team tracking, and single sign on for events.

By registering your CTF event with MajorLeagueCyber users can automatically login, track their individual and team scores, submit writeups, and get notifications of important events.

To integrate with MajorLeagueCyber, simply register an account, create an event, and install the client ID and client secret in the relevant portion in `CTFd/config.py` or in the admin panel:

```python
OAUTH_CLIENT_ID = None
OAUTH_CLIENT_SECRET = None
>>>>>>> CTFd/master
```

脚本第一次执行时会自动初始化配置，初始化后将无法自动修改，你需要手动根据sed.sh脚本修改相应的值或后台配置

```
sudo apt install git -y
git clone https://github.com/huangzheng2016/CTFd-docker CTFd
vi CTFd/docker-compose.yml
#修改CTFD_URL、DIRECT_URL、DYNAMIC_URL，并在DNS服务器上做解析
sudo sh CTFd/install.sh
```

虽然还是建议大家自己安装，别直接脚本，以免出现配置不正确

请在root权限下执行

```
apt-get update
apt-get install git docker docker-compose -y
#如果docker安装失败
#apt-get install git docker.io docker-compose -y
git clone https://github.com/huangzheng2016/CTFd-docker CTFd
docker swarm init --advertise-addr 127.0.0.1
docker node update --label-add='name=linux-1' $(docker node ls -q)
docker-compose -f CTFd/docker-compose.yml up -d
```

## 更新日志

2024.1.19
>修改默认主题为core
>
>core-beta主题暂不支持（等官方beta版搞完再做适配）

