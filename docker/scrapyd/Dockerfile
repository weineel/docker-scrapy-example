# Author: weineel
FROM python:2.7.13

MAINTAINER weineel LiJF_wn@163.com

WORKDIR /var/code

# COPY/ADD(可以是一个压缩包，会自动解压)
COPY ./etc/pip.conf /root/.pip/pip.conf
COPY ./etc/scrapyd.conf /etc/scrapyd/scrapyd.conf

RUN pip install --no-cache-dir scrapy scrapyd

# 定义编译指令
# 在编译时通过 docker build --build-arg _TZ=Asia/Shanghai,_TC=weiguo -t test_python:1.0.0 . 方式指定，
# 可以用在run等指令中，做分支判断
ARG _TZ=Asia/Shanghai
ARG _TC
# 在启动容器是 -e 指定环境变量，会覆盖编译时赋的值。
ENV TZ $_TZ
ENV TC $_TC

VOLUME /var/code

EXPOSE 6800

# ENTRYPOINT ["/bin/bash"]
# ENTRYPOINT 和 CMD的区别
# 相当于开机启动项，container在启动时执行
CMD ["scrapyd", "--pidfile="]
