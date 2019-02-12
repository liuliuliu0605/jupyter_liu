1.使用环境
gw000/keras-full容器

2.开启方式
(a)设置环境变量
vim ~/.bashrc
export JUPYTER_LIU='/path/to/juypter_liu'
source ~/.bashrc
(b)开启容器
docker run -d $(ls /dev/nvidia* | xargs -I{} echo '--device={}') $(ls /usr/lib/*-linux-gnu/{libcuda,libnvidia}* | xargs -I{} echo '-v {}:{}:ro') -p 8888:8888 -v $JUPYTER_LIU:/srv -v $JUPYTER_LIU/.keras:/home/user/.keras gw000/keras-full
(c)几点说明
keras文件夹存放项目
.keras文件夹存放缓存的深度学习模型

