FROM alpine:3.15.0

RUN apk add --no-cache \
  bash \
  curl \
  gcc

RUN curl --proto "=https" --tlsv1.2 -sSf https://sh.rustup.rs -o /tmp/sh.rustup.rs \
  && chmod +x /tmp/sh.rustup.rs \
  && /tmp/sh.rustup.rs --default-toolchain none -y \
  && rm -rf /tmp/sh.rustup.rs \
  && . "$HOME"/.cargo/env \
  && rustup toolchain install nightly \
  && rustup component add rust-analyzer-preview

COPY ./docker_entrypoint.sh /docker_entrypoint.sh

ENTRYPOINT [ "/docker_entrypoint.sh" ]

CMD [ "/root/.rustup/toolchains/nightly-x86_64-unknown-linux-musl/bin/rust-analyzer" ]
