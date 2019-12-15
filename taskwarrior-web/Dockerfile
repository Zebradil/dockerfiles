FROM alpine

RUN apk add --no-cache task ruby python \
 && apk add --no-cache --virtual .build-dependencies ruby-dev make g++ \
 && gem install taskwarrior-web --no-document \
 && apk del --no-cache .build-dependencies \
 && echo '*/5    *       *       *       *       task sync' > /etc/crontabs/root

VOLUME ["/root/.taskrc"]

EXPOSE 5678

CMD task sync && task-web -L -F
