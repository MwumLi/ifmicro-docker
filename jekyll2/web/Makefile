JEKYLL_HTML=/opt/jekyll/html

# 运行项目, 随机分配宿主机端口
# 查看端口绑定使用 : make port
random:
	sudo docker run --rm  -p 4000 --name jekyll2 -v ${PWD}/md:/opt/jekyll/md -v ${PWD}/html:/opt/jekyll/html mwumli/jekyll:v2 || make exec_run

# 运行项目: 绑定容器端口 4000 到宿主机 4000 端口
run:
	sudo docker run --rm  -p 4000:4000 --name jekyll2 -v ${PWD}/md:/opt/jekyll/md -v ${PWD}/html:/opt/jekyll/html mwumli/jekyll:v2 || make exec_run

exec_run:
	sudo docker exec jekyll2 jekyll serve --watch -H 0.0.0.0 --destination=${JEKYLL_HTML} || echo "May be you need 'make entry'"

# 命令提示符交互模式进入 jekyll2 容器
entry:
	sudo docker exec -it jekyll2 bash || make entry_run

entry_run:
	sudo docker run -it --rm  -p 4000:4000 --name jekyll2 -v ${PWD}/md:/opt/jekyll/md -v ${PWD}/html:/opt/jekyll/html mwumli/jekyll:v2 bash 

# 停止 jekyll2 容器
stop:
	sudo docker stop jekyll2 

# 清除 jekyll2 容器 并 清除目录 html/
clean:
	sudo docker rm jekyll2 ; rm -rvf html/*

# 显示容器 jekyll2 的容器端口与宿主机的绑定信息
port:
	sudo docker port jekyll2
