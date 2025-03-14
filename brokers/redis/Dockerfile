# Используем официальный образ Redis
FROM redis:latest

# Устанавливаем Python 3.10.11
USER root
RUN apt-get update && apt-get install -y python3.10 python3-pip python3.10-dev && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1
RUN pip3 install --upgrade pip && pip3 install redis==5.0.1

# Копируем конфигурацию
COPY redis.conf /usr/local/etc/redis/redis.conf

# Порт
EXPOSE 6379

# Команда запуска
CMD ["redis-server", "/usr/local/etc/redis/redis.conf"] 
