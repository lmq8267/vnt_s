<div align="center">
  <a href="https://rustvnt.com">
<img src="https://socialify.git.ci/lmq8267/vnt_s/image?custom_description=vnt%E7%9A%84%E6%9C%8D%E5%8A%A1%E7%AB%AF%EF%BC%8C%E5%9B%BA%E5%8C%96%E4%BF%9D%E5%AD%98wireguard%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%EF%BC%8C%E4%B8%94%E5%B7%B2%E6%94%AF%E6%8C%81wg%E8%AE%BF%E9%97%AEvnt%E5%86%85%E5%AD%90%E7%BD%91%E8%AE%BE%E5%A4%87%EF%BC%81&description=1&font=Rokkitt&forks=1&issues=1&logo=https%3A%2F%2Fraw.githubusercontent.com%2Flmq8267%2FVntApp%2Fmaster%2Fandroid%2Fapp%2Fsrc%2Fmain%2Fres%2Fmipmap-xxxhdpi%2Fic_launcher.png&name=1&owner=1&pattern=Plus&pulls=1&stargazers=1&theme=Auto" alt="vnt_s" width="640" height="320" /></a>
<div>
  
# 服务端vnts
<p align="center">
  <img alt="" src="https://img.shields.io/github/created-at/lmq8267/vnt_s?logo=github&label=%E5%88%9B%E5%BB%BA%E6%97%A5%E6%9C%9F">
<a href="https://github.com/lmq8267/vnt_s/releases"><img src="https://img.shields.io/github/downloads/lmq8267/vnt_s/total?logo=github&label=%E4%B8%8B%E8%BD%BD%E9%87%8F"></a>
<a href="https://github.com/lmq8267/vnt_s/graphs/contributors"><img src="https://img.shields.io/github/contributors-anon/lmq8267/vnt_s?logo=github&label=%E8%B4%A1%E7%8C%AE%E8%80%85"></a>
<a href="https://github.com/lmq8267/vnt_s/releases/"><img src="https://img.shields.io/github/release/lmq8267/vnt_s?logo=github&label=%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC"></a>
<a href="https://github.com/lmq8267/vnt_s/issues"><img src="https://img.shields.io/github/issues-raw/lmq8267/vnt_s?logo=github&label=%E9%97%AE%E9%A2%98"></a>
<a href="https://github.com/lmq8267/vnt_s/actions?query=workflow%3ABuild"><img src="https://img.shields.io/github/actions/workflow/status/lmq8267/vnt_s/CI.yml?branch=master&logo=github&label=%E6%9E%84%E5%BB%BA%E7%8A%B6%E6%80%81" alt=""></a>
<a href="https://hub.docker.com/r/lmq8267/vnt_s"><img src="https://img.shields.io/docker/pulls/lmq8267/vnts?color=%2348BB78&logo=docker&label=%E6%8B%89%E5%8F%96%E9%87%8F" alt=""></a>
</p>
  
客户端https://github.com/lmq8267/vnt-Redir


下载 点右边的releases

### Docker部署

> 下述命令中的 `/你的宿主机文件目录` 是你宿主机里的目录，主要是用来保存在web页面添加的WireGuard客户端配置文件，防止重启或更新容器数据丢失导致添加过的WireGuard客户端失效

- cmd 

  `docker run --name vnts -v /你的宿主机文件目录:/usr/bin/vnts_wg -p 29872:29872/tcp -p 29872:29872/udp -p 29870:29870/tcp -e TZ=Asia/Shanghai --restart=always -d lmq8267/vnts -p 29872 -P 29870 -U WEB用户名 -W WEB密码`

- compose.yaml

```
version: '3.9'
services:
    vnts:
        image: lmq8267/vnts
        container_name: vnts
        restart: always
        ports:
            - '29870:29870/tcp'
            - '29872:29872/tcp'
            - '29872:29872/udp'
        volumes:
            - '/你的宿主机文件目录:/usr/bin/vnts_wg'
        environment:
            - TZ=Asia/Shanghai
        command: '-p 29872 -P29870 -U WEB用户名 -W WEB密码'
```
