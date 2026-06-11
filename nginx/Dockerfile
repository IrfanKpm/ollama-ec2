FROM nginx:alpine

RUN apk add --no-cache gettext

COPY nginx.conf /etc/nginx/nginx.conf.template

# At container start: inject API_SECRET_KEY into nginx config, then run nginx
CMD ["/bin/sh", "-c", "envsubst '${API_SECRET_KEY}' < /etc/nginx/nginx.conf.template > /etc/nginx/nginx.conf && nginx -g 'daemon off;'"]