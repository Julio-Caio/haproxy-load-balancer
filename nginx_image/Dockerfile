FROM debian:12

# Instalar NGINX
RUN apt-get update && apt-get install -y nginx && apt-get clean

# Copiar arquivos da aplicação
COPY . /usr/share/nginx/html

# Expor a porta 80
EXPOSE 80

# Iniciar o NGINX
CMD ["nginx", "-g", "daemon off;"]
