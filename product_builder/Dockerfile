FROM golang:latest
RUN  adduser \
   --system \
   --shell /bin/bash \
   --disabled-password \
   --home /app goserver && \
	chown -R goserver /app
WORKDIR /app

COPY *.go ./
RUN go mod init goserver
RUN go mod tidy
RUN go build -o goserver .
USER goserver

ENV PGHOST="products-postgresql.gb-backend1-dev.svc.cluster.local"
ENV PGPORT="5432"
ENV APP_DB_USERNAME=techuser
ENV APP_DB_PASSWORD=techuser
ENV APP_DB_NAME=products
ENV TEST_DB_USERNAME=$APP_DB_USERNAME
ENV TEST_DB_PASSWORD=$APP_DB_PASSWORD
ENV TEST_DB_NAME=$APP_DB_NAME

EXPOSE 8010
CMD ["./goserver"]