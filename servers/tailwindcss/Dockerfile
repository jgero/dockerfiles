FROM alpine:3.15.0

RUN apk add --no-cache \
	nodejs \
	npm \
	&& npm install -g \
	tailwindcss \
	@tailwindcss/language-server

CMD ["tailwindcss-language-server", "--stdio"]
