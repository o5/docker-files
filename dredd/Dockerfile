FROM node:9.4-alpine
MAINTAINER Petr Bugyík

RUN apk add --no-cache \
        make \
        gcc \
        g++ \
        python \
        git \
    && \
    npm install dredd@"~4.9" && \
    apk del \
        make \
        gcc \
        g++ \
        python \
        git \
    && \
    npm cache --force clean && \
    rm -rf node_modules/faker && \
    find node_modules \
        -not \( -path node_modules/chai/lib -prune \) \
        -not \( -path node_modules/rx -prune \) \
        \( \( -iname "readme*" -or -iname "changelog*" -or -iname "test*.js" -or -iname "*.min.js" \) -and -type f \) -or \
        \( \( -iname "dist" -or -iname "min" -or -iname "test*" -or -iname "doc*" -or -iname "example*" -or -iname "build" -or -iname "benchmark*" \) -and -type d \) \
    | xargs rm -rf

ENTRYPOINT ["/node_modules/.bin/dredd"]
