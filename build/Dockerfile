FROM alpine
WORKDIR /root
RUN apk add build-base git \
    && git clone https://github.com/Wind4/vlmcsd.git \
    && cd vlmcsd \
    && make

FROM alpine
COPY --from=0 /root/vlmcsd/bin/vlmcsd .
CMD ["./vlmcsd","-e","-D","-d"]