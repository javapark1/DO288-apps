# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
      io.kis.display-name="Apache HTTP server" \
      io.openshift.expose-service="8080:http" \
      io.openshift.tags="apache, httpd"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

# Add an unprivileged user. Red Hat convention: 1001
USER 1001
