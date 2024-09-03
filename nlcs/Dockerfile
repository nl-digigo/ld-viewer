FROM alpine:3.19


RUN apk update && \
    apk add --update --no-cache openjdk8 && \
    apk add --update --no-cache apache-ant && \
    apk add --update --no-cache curl zip unzip && \
    apk add --update --no-cache python3 py3-pip

RUN apk add --no-cache aws-cli
RUN rm -rf /var/cache/apk/*
RUN aws --version

CMD ["/bin/bash"]
