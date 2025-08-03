# Использую образ убунты v22.04
FROM ubuntu:22.04

# Установка nginx и очистка кеша
RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Копируем конфиг
COPY my_site.conf /etc/nginx/sites-available/

# Создаём директорию и копируем index.html
RUN mkdir -p /var/www/my_site
COPY index.html /var/www/my_site/

# Активируем конфиг
RUN ln -s /etc/nginx/sites-available/my_site.conf /etc/nginx/sites-enabled/

# Удаляем дефолтный конфиг nginx
RUN rm /etc/nginx/sites-enabled/default

# Указываем на каком порту будут работать контейнеры
EXPOSE 80

# Запускаем nginx в foreground режиме
CMD ["nginx", "-g", "daemon off;"]