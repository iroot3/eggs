FROM        --platform=$TARGETOS/$TARGETARCH node:22-alpine

LABEL       org.opencontainers.image.source="https://github.com/iroot3/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache ca-certificates curl ffmpeg git openssl sqlite tar tzdata \
			&& adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

RUN			git clone https://github.com/Lissy93/dashy.git \
            && npm install --global / yarn \
			&& cd dashy \
			&& yarn

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]