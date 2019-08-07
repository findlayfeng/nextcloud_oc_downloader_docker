FROM nextcloud:fpm-alpine

RUN apk add --no-cache aria2-daemon youtube-dl && \
	ln -s /usr/bin/youtube-dl /usr/local/bin/ && \
	mkdir /var/log/aria2c /var/local/aria2c && \
	touch /var/log/aria2c/aria2c.log && \
	touch /var/local/aria2c/aria2c.sess && \
	chown www-data.www-data -R /var/log/aria2c /var/local/aria2c && \
	chmod 770 -R /var/log/aria2c /var/local/aria2c

COPY aria2c.sh /
RUN chmod +x /aria2c.sh

ENTRYPOINT ["/aria2c.sh"]
CMD ["php-fpm"]