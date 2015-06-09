FROM hidai620/centos7-systemd

MAINTAINER "Yoshiaki Hidai" <hidai.620@gmail.com>

WORKDIR /app

RUN yum install epel-release -y \
        gcc \
        glibc-devel \
        make \
        ncurses-devel \
        openssl-devel \ 
        initscripts \
        logrotate \ 
        wget \ 
        tar \ 
        make \ 
        zlib-devel \ 
        openssl-devel \ 
        libffi-devel && \ 
    wget https://ftp.ruby-lang.org/pub/ruby/ruby-2.2.2.tar.gz && \
    tar xzf ruby-2.2.2.tar.gz && \
    cd ruby-2.2.2 && \
    ./configure && \
    make && \
    make install && \
    ln -s /usr/local/bin/ruby /usr/bin/ruby 

EXPOSE 5672

# CMD ["/usr/sbin/init"]
CMD ["ruby", "-v"]
