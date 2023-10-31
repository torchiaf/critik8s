# Build
FROM golang:alpine AS build
ADD . /app
RUN cd /app && go build -o emit

# Deploy
FROM alpine
WORKDIR /emit
COPY --from=build /app /emit
ENTRYPOINT ["./emit"]