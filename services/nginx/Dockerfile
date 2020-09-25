FROM nginx:1.17-alpine
RUN addgroup -g 1333 vscoder && addgroup nginx vscoder
RUN adduser -u 1333 -S vscoder -G vscoder
COPY default.conf /etc/nginx/conf.d/default.conf
