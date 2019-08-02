FROM centos:7.6.1810

#定义时区参数
ENV TZ=Asia/Shanghai
#设置时区
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo '$TZ' > /etc/timezone
#设置编码
RUN localedef -c -f UTF-8 -i zh_CN zh_CN.utf8
#设置环境变量
ENV LC_ALL zh_CN.utf8
#设置安装仓库
COPY centos/7.6/CentOS-Base.repo  /etc/yum.repos.d/