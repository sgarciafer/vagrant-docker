FROM mhart/alpine-node:5

RUN apk add --update bash openssl git perl python build-base
RUN apk add gosu --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ 
RUN addgroup cubein && adduser -s /bin/bash -D -G cubein cubein

ADD data/ /home/app/data
ENV HOME=/home/app/data
WORKDIR $HOME

RUN npm install
RUN chown -R cubein:cubein $HOME/* 
EXPOSE 80

CMD ["gosu", "cubein", "node", "index.js"]
