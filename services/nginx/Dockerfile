FROM nginx:1.17-alpine
RUN addgroup -g 1000 vscoder && addgroup nginx vscoder
RUN adduser -u 1000 -S vscoder -G vscoder
COPY default.conf /etc/nginx/conf.d/default.conf
