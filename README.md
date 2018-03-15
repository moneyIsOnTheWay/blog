# blog
node + hexo + docker + nginx搭建的个人博客

### 博客预览 [http://123.207.19.115](http://123.207.19.115)

## 搭建方法

### 环境

- 安装node (针对linux。window安装一键化，不罗嗦)

`
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
`

> 退出终端重新进入安装

`
nvm install stable
`

> 安装hexo

`
npm install -g hexo-cli
`

- docker安装并启动（官网有详细教程，不罗嗦）

`
yum install docker-ce 
sudo systemctl restart docker
`

- 挂载hexo的public文件到docker启动的nginx服务器

`
docker run –name nginx -p 80:80 -v /home/wll/blog/public:/usr/share/nginx/html -d nginx
`

> 上面/home/wll/是我blog项目放在服务器上的目录，如需更新public的静态文件只需hexo g命令即可