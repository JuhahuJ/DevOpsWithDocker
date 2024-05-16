FROM ubuntu

EXPOSE 8080

WORKDIR /usr/src/app

COPY /go1.22.2.linux-amd64.tar.gz ./

ENV PATH=$PATH:/usr/local/go/bin

COPY /example-backend ./

ENV REQUEST_ORIGIN=http://localhost:5000

RUN tar -C /usr/local -xzf go1.22.2.linux-amd64.tar.gz && apt-get update && apt-get install -y ca-certificates && go build && useradd -m appuser && rm go1.22.2.linux-amd64.tar.gz

USER appuser

CMD ./server
