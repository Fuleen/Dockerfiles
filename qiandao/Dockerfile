FROM multiarch/debian-debootstrap:arm64-sid-slim

RUN sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list \
  && sed -i 's|cdn-fastly.deb.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list \
  && sed -i 's|security.debian.org/debian-security|mirrors.aliyun.com/debian-security|g' /etc/apt/sources.list \
  
  && apt update \
  && apt-get -y install autoconf g++ python-dev python-pip python-pbkdf2 git \

  && cd / && git clone https://github.com/binux/qiandao.git && pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --no-cache-dir -r /qiandao/requirements.txt \

  && apt-get purge -y --auto-remove autoconf g++ git \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR /qiandao

VOLUME ["/qiandao/"]

ENV PORT 80
EXPOSE $PORT/tcp

CMD ["python","/qiandao/run.py"]