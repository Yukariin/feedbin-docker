FROM ruby:alpine

ARG FEEDBIN_URL

WORKDIR /app

RUN apk add --no-cache \
	build-base \
	libidn-dev \
	libpq-dev \
	postgresql-dev \
	postgresql-client \
	nodejs \
	imagemagick \
	vips \
	tzdata \
	git

RUN git clone https://github.com/feedbin/feedbin.git /app && rm -rf /app/.git

RUN bundle install

RUN bundle exec rake assets:precompile

ENV RAILS_SERVE_STATIC_FILES=true

CMD ["bundle", "exec", "foreman", "start"]
