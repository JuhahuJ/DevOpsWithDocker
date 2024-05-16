FROM docker
RUN apk update
RUN apk add git && apk add bash
WORKDIR /app
COPY ./script.sh .
RUN chmod +x ./script.sh
ENTRYPOINT ["/bin/bash", "/app/script.sh"]
