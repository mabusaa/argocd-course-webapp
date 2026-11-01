# MULTIENV
FROM golang:1.27-alpine AS build
WORKDIR /src
COPY go.mod webapp.go ./
RUN CGO_ENABLED=0 go build -o /webapp .

FROM alpine:3.20
COPY --from=build /webapp /webapp
EXPOSE 8080
ENTRYPOINT ["/webapp"]
