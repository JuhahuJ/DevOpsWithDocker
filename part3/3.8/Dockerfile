FROM node:16-alpine as build

WORKDIR /usr/src/app

COPY /example-frontend ./

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm install && npm run build


FROM node:16-alpine

EXPOSE 5000

WORKDIR /usr/src/app

RUN npm install -g serve && adduser -D appuser

USER appuser

COPY --from=build /usr/src/app/build /usr/src/app/build

CMD ["serve", "-s", "-l", "5000", "build"]
