FROM docker.io/fedora
RUN mkdir -p /var/www && \
    mkdir -p /var/www/html
ADD index.html /var/www/html
RUN dnf install -y httpd && \
    dnf clean all
CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
