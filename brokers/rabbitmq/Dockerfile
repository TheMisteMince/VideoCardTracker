# Используем официальный образ RabbitMQ
FROM rabbitmq:3.12-management

# Устанавливаем Python 3.10.11
USER root
RUN apt-get update && apt-get install -y python3.10 python3-pip python3.10-dev && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1
RUN pip3 install --upgrade pip && pip3 install pika==1.3.2

# Копируем конфигурацию
COPY rabbitmq.conf /etc/rabbitmq/rabbitmq.conf

# Порты
EXPOSE 5672 15672

# Команда запуска
CMD ["rabbitmq-server"] 
