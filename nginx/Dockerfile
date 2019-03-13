FROM nginx:1.14-alpine
LABEL maintainer="xiaoxin008 <wangfangxin01@163.com>"

ENV NGINX_DOC_ROOT='/data/web/html/'

WORKDIR ./

ADD index.html ${NGINX_DOC_ROOT}
ADD init.sh /bin/

EXPOSE 80/tcp

HEALTHCHECK --start-period=3s CMD wget -o - -q http://${IP:-0.0.0.0}/

CMD ["/user/sbin/nginx","-g","daemon off;"]

ENTRYPOINT ["/bin/init.sh"]