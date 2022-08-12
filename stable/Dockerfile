FROM ubuntu

RUN apt update && DEBIAN_FRONTEND=noninteractive apt install -y python3-pip \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 --no-cache-dir install --upgrade pip \
  && rm -rf /var/lib/apt/lists/* /var/cache/* \
  && useradd --system py-user \
  && mkdir -p /home/py-user/data \
  && chown -R py-user:py-user /home/py-user

# Use C.UTF-8 locale to avoid issues with ASCII
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

WORKDIR /home/py-user/data
ENV HOME /home/py-user

ENV USER py-user
USER py-user
ENV PATH /home/py-user/.local/bin:$PATH

CMD [ "/bin/bash" ]
