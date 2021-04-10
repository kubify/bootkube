FROM golang:1.16.3 AS builder

WORKDIR /bootkube
COPY . .
ENV GO111MODULE=on
RUN make

FROM alpine:3.13.4

WORKDIR /

COPY --from=builder /bootkube/_output/bin/linux/bootkube /bootkube
