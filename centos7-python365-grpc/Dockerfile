FROM centos:7
COPY resources /
RUN mv pip.conf /etc/pip.conf && \
    yum update  -y && yum install -y wget make gcc zlib* openssl-devel sqlite-devel bzip2-devel xz-devel python-backports-lzma && \
    tar -zxvf Python-3.6.5.tgz && \
    cd Python-3.6.5 && \
    ./configure --enable-loadable-sqlite-extensions && \
    make && make install && \
    rm -rf /Python-3.6.5*
RUN mv lzma.py /usr/local/lib/python3.6/lzma.py
RUN pip3 install -r  requirements.txt
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && pip3 install --upgrade pip && pip3 install -r requirements.txt

CMD ["python3"]
