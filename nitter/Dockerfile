FROM 'quay.io/unixfox/nitter'

COPY ./nitter.conf /src/nitter.conf

WORKDIR /src/app

RUN apk --no-cache add redis caddy python

ENV overmind=overmind-v2.3.0-linux-amd64

RUN wget https://github.com/DarthSim/overmind/releases/download/v2.3.0/${overmind}.gz && \
    gunzip ${overmind}.gz && chmod +x ${overmind}

COPY ./Procfile ./

COPY ./Caddyfile ./

CMD /src/app/${overmind} start
