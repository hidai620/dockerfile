FROM hidai620/centos7-systemd

WORKDIR /app

RUN rpm -Uvh https://www.rabbitmq.com/releases/erlang/erlang-17.4-1.el6.x86_64.rpm && \
    yum install epel-release -y \
        gcc \
        glibc-devel \
        make \
        ncurses-devel \
        openssl-devel \ 
        erlang \
        initscripts \
        logrotate && \ 
    rpm --import http://www.rabbitmq.com/rabbitmq-signing-key-public.asc && \
    rpm -Uvh http://www.rabbitmq.com/releases/rabbitmq-server/v3.2.1/rabbitmq-server-3.2.1-1.noarch.rpm && \
    /etc/init.d/rabbitmq-server start

EXPOSE 5672

CMD ["/usr/sbin/init"]
