FROM alpine:3.10

RUN apk add --update --no-cache nginx
RUN rm /etc/nginx/conf.d/default.conf

COPY docker/nginx/nginx.conf /etc/nginx/
COPY docker/nginx/site.conf /etc/nginx/conf.d/

ADD ./index.html /var/www/html/

RUN adduser -D -g '' -G www-data www-data
RUN chown -R www-data:www-data /var/tmp/nginx

CMD ["nginx"]

EXPOSE 8088
