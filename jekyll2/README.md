Last Update: 2016-03-08 17:18:38

## 简介

这是一个 jekyll2 的最新版本 v2.5.3 的镜像  

目前 jekyll 最新版本是 v3.1.2  

最新版本可到 <https://jekyllrb.com/docs/history/> 查看  


## jekyll 是什么  

jekyll 是一个静态博客工具, 可以将纯文本(Markdown)转化为静态网站和博客  

jekyll 中文站点 : <http://jekyll.bootcss.com/>  
jekyll 官方站点 : <https://jekyllrb.com/>  
jekyll 快速使用 : <http://www.ifmicro.com/static-website-by-jekyll/>  
Github Page 服务 : <https://pages.github.com/>

## 使用

* 生成此 docker 镜像 :  `sudo docker build -t="user/image:tag" .`  
* 运行 jekyll2 项目 :   
  1. 复制当前目录下的 `web/` 文件夹  
  2. 进入 `web/` 下, 把你的 jekyll2 项目放入 `web/md/` 下  
  3. 在 `web/` 下运行项目 : `make run`  
  4. 生成的 HTMl 文件存放在 `web/html/` 下  
  5. `web` 的名字可以更换, 但是 `web` 内部的目录结构请不要随意更换  
  6. 如果想停止镜像运行 : `make stop`
  7. `web/Makefile` 是我对 docker 的不同命令的简易封装, 其他操作请查看 `Makefile`  
     (确保你已经安装了 `make`)  
* 此镜像已经上传 hub docker, 你也可以直接 pull : `sudo docker pull mwumli/jekyll:v2`  


