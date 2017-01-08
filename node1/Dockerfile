FROM mhart/alpine-node:5

RUN apk add --update bash openssl git perl python build-base \
&& apk add gosu --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ \
&& apk add dockerize --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/community \
&& addgroup dashboard && adduser -s /bin/bash -D -G cubein cubein

ADD data/ /home/app/data
ENV HOME=/home/app/data
WORKDIR $HOME

RUN npm install \
&& chown -R cubein:cubein $HOME/* \
&& gosu cubein npm install \
EXPOSE 80

CMD ["gosu", "cubein", "node", "index.js"]
