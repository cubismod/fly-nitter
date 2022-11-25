FROM 'zedeus/nitter'

COPY ./nitter.conf /src/nitter.conf

WORKDIR /src/app

RUN apk --no-cache add redis python3 nginx

RUN python3 -m ensurepip && python3 -m pip install supervisor

RUN mkdir /src/app/cache

COPY ./supervisord.conf ./ 
COPY ./nginx.conf ./

CMD [ "supervisord", "-c", "./supervisord.conf" ]
