FROM ruby:alpine

WORKDIR /app

RUN apk add --no-cache \
	build-base \
	git

RUN git clone https://github.com/feedbin/privacy-please.git /app && rm -rf /app/.git

RUN bundle install

CMD ["bundle", "exec", "foreman", "start"]
