FROM nginx:1.14-alpine
LABEL maintainer="xiaoxin008 <wangfangxin01@163.com>"

ENV NGINX_DOC_ROOT='/data/web/html/'

ADD index.html ${NGINX_DOC_ROOT}
ADD init.sh /bin/

RUN chmod 777 /bin/init.sh

EXPOSE 80/tcp

HEALTHCHECK --start-period=3s CMD wget -o - -q http://${IP:-0.0.0.0}/

CMD ["/user/sbin/nginx","-g","daemon off;"]

ENTRYPOINT ["/bin/init.sh"]