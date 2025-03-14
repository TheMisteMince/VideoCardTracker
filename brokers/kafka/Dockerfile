# Используем базовый образ с Kafka
FROM wurstmeister/kafka:latest

# Устанавливаем Python 3.10.11
USER root
RUN apt-get update && apt-get install -y python3.10 python3-pip python3.10-dev && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1
RUN pip3 install --upgrade pip && pip3 install kafka-python==2.0.2

# Копируем кастомные скрипты (если есть)
COPY kafka-config.yaml /etc/kafka/kafka-config.yaml

# Переключаемся на пользователя Kafka
USER kafka

# Порты
EXPOSE 9092

# Команда запуска
CMD ["sh", "-c", "kafka-server-start.sh /etc/kafka/kafka-config.yaml"]
