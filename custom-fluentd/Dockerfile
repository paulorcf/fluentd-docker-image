FROM my.paulorcf.com:8082/fluent/fluentd:v0.12.39-onbuild
MAINTAINER Paulo Castro <paulo@memorelab.com>

RUN apk add --update --virtual .build-deps \
        sudo build-base ruby-dev libffi libffi-dev \

 && sudo gem install ffi \
 # cutomize following instruction as you wish
 && sudo gem install \
        fluent-plugin-secure-forward \
 && sudo gem install \
		fluent-plugin-kafka \
 
 && sudo gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/* \
           /home/fluent/.gem/ruby/2.3.0/cache/*.gem

EXPOSE 24284
