FROM amazoncorretto:8-alpine3.19-jre AS build

WORKDIR /usr/src/app

COPY /spring-example-project ./

RUN apk update && apk add maven && mvn package


FROM amazoncorretto:8-alpine3.19-jre

EXPOSE 8080

WORKDIR /usr/src/app

COPY --from=build /usr/src/app/target/docker-example-1.1.3.jar ./docker-example.jar

RUN adduser -D appuser

USER appuser

CMD java -jar docker-example.jar

