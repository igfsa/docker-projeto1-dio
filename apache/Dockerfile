FROM httpd:2.4

# Cria o diretório extra, se não existir
RUN mkdir -p /usr/local/apache2/conf/extra

# Habilita os módulos de proxy
RUN sed -i '/#LoadModule proxy_module/s/^#//' /usr/local/apache2/conf/httpd.conf \
    && sed -i '/#LoadModule proxy_http_module/s/^#//' /usr/local/apache2/conf/httpd.conf \
    && sed -i '/#LoadModule proxy_connect_module/s/^#//' /usr/local/apache2/conf/httpd.conf \
    && sed -i '/#LoadModule proxy_ftp_module/s/^#//' /usr/local/apache2/conf/httpd.conf

# Inclui o arquivo de configuração
RUN echo "Include conf/extra/my-proxy.conf" >> /usr/local/apache2/conf/httpd.conf

# Copia a página inicial
COPY index.html /usr/local/apache2/htdocs/index.html

# Garante permissões de leitura para todos
RUN chmod 644 /usr/local/apache2/htdocs/index.html