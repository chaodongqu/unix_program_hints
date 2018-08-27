http://oyvindsk.com/writing/docker-build-from-source

https://github.com/moby/moby/issues/33669

### A  golang安装：go1.10.3.linux-amd64.tar.gz

### B: debian安装 docker(直接下载安装包）
https://www.cnblogs.com/heyangyi/p/8613149.html 
<br>
docker-ce_18.06.1~ce~3-0~debian_amd64.deb

注意：<br>
修改PATH

问题：(本质原因是，通过 dockerhub的版本与本地版本不一致） 参考回答 ：<br>https://github.com/ethereum/go-ethereum/issues/15363<br>
Error parsing reference: golang:1.10.3 AS base is not a valid repository/tag: invalid reference format
<br>--- 切换到最新版本
<br> docker-ce_18.06.1~ce~3-0~debian_amd64.deb

#### C。 编译源码
下载 git docker 
make build
make binary

### D. 验证docker：
1 . 编译结果放在 ~/work/mdoc/moby/bundles/binary-daemon$ 
2  先stop 原来的docker
3 . 执行 ./bundles/binary-daemon/docerkd
4 . 执行  sudo docker version

```
Client:
 Version:           18.06.1-ce
 API version:       1.38
 Go version:        go1.10.3
 Git commit:        e68fc7a
 Built:             Tue Aug 21 17:23:18 2018
 OS/Arch:           linux/amd64
 Experimental:      false

Server:
 Engine:
  Version:          dev
  API version:      1.38 (minimum version 1.12)
  Go version:       go1.10.3
  Git commit:       1fd7e4c28
  Built:            Fri Aug 24 00:44:05 2018
  OS/Arch:          linux/amd64
  Experimental:     false

```
--------------- 已经OK

https://jimmysong.io/posts/docker-dev-env/

### 其他问题，golang的开发环境配置
golang 的 vs code 环境配置很折腾(一定要设置代理）
```
chaodongqu@chaodongqu:~/tmp$ http_proxy=http://127.0.0.1:9666 go get -u golang.org/x/tools/cmd/gorename
https://blog.csdn.net/littlebrain4solving/article/details/78871137


```