FROM alpine:latest

RUN mkdir /app

COPY mail-service/mailServiceApp /app
COPY mail-service/templates /templates

CMD [ "/app/mailServiceApp"]