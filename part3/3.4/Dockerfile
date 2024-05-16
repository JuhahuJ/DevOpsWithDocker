FROM docker
RUN apk update
RUN apk add git && apk add bash
WORKDIR /app
COPY ./script.sh .
RUN chmod +x ./script.sh
ENTRYPOINT ["/bin/bash", "/app/script.sh"]

# the command to run this container
# docker run -it -v /var/run/docker.sock:/var/run/docker.sock <Docker image> <Github repository> <dockerhub repository>
