

# 运行docker 进入一个 ubuntu17.10系统的容器命令行
    sudo docker run -it ubuntu:17.10 /bin/bash

# 查看容器进程
    sudo docker ps

# 查看容器标准输出
    sudo docker logs 2b1b7a428627

# 终止docker容器
    sudo docker stop container_name/container_id

# 启动被终止的docker容器
    sudo docker start container_name/container_id

# 本机镜像列表
    sudo docker images

# 查找镜像
    sudo docker search mysql

# 下载镜像
    sudo docker pull mysql:5.6

# 运行mysql镜像
    sudo docker run --name mysql -p 3305:3306 -e MYSQL_ROOT_PASSWORD=12345abc -d mysql:5.5

    sudo docker run -d -p8080:80 -v /home/silk/htdocs/8net:/var/www/html grass/apache:php55
    
    sudo docker run -d -p8080:80 -v /usr/local/var/www/cn-8net:/var/www/html --link mysql grass/apache:php55-ioncube

    sudo docker run -d -p8080:80 -v /usr/local/var/www/acer_PAP_EC:/var/www/html -v /usr/local/var/www/acer_PAP_EC/app.conf:/etc/apache2/sites-enabled/app.conf --link mysql57 grass/apache:php55-ioncube
    

# 进入docker容器
    sudo docker exec -it mysql bash

# docker内访问mysql
    mysql -uroot -p123456

# 本地访问mysql
    mysql -h192.168.0.104 -P12345 -uroot -p123456

# 删除容器
    sudo docker rm e9c677cfc75e

# 删除镜像
    sudo docker rmi mysql:5.5

# 创建镜像
    sudo docker build -t image_name .

ElasticSearch:
    docker run --restart=always -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.7.1

    docker run --restart=always -d --name redis -p 6379:6379 redis