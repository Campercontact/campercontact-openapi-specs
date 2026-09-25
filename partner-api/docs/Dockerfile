# Build context is partner-api/, so no other spec in this repo can end up in the public image
FROM nginx:1.29-alpine

COPY docs/nginx.conf /etc/nginx/nginx.conf.template
RUN rm /usr/share/nginx/html/*
COPY docs/index.html docs/logo.svg docs/logo-white.svg docs/favicon.svg docs/robots.txt documentation.yaml /usr/share/nginx/html/

ENV PORT=8080
CMD ["sh", "-c", "sed \"s/__PORT__/$PORT/\" /etc/nginx/nginx.conf.template > /tmp/nginx.conf && exec nginx -c /tmp/nginx.conf -g 'daemon off;'"]
