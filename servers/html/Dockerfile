FROM alpine:3.15.0

RUN apk add --no-cache \
  nodejs \
  npm \
  && npm install -g \
    vscode-html-languageserver-bin

CMD [ "html-languageserver", "--stdio" ]
