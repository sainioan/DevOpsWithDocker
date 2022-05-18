FROM golang:1.16.0-alpine
EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

# Build project
RUN go build

CMD ./server
