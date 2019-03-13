FROM nginx:1.14-alpine
LABEL maintainer="xiaoxin008 <wangfangxin01@163.com>"

ENV NGINX_DOC_ROOT=/data/web/html/
ENV PORT=8080

ADD index.html ${NGINX_DOC_ROOT}
ADD init.sh /bin/

RUN chmod +x /bin/init.sh

EXPOSE ${PORT}/tcp

HEALTHCHECK --start-period=3s CMD wget -O - -q http://${IP:-0.0.0.0}:${PORT}/

CMD ["/usr/sbin/nginx","-g","daemon off;"]

ENTRYPOINT ["/bin/init.sh"]