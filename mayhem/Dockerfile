FROM --platform=linux/amd64 ubuntu:20.04 as builder

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y build-essential python

COPY . /repo
WORKDIR /repo
RUN make shoco

FROM ubuntu:20.04 as package
COPY --from=builder /repo/shoco /
