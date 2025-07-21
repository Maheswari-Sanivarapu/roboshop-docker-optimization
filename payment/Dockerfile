FROM python:3.9.23-alpine3.22
EXPOSE 8080
WORKDIR /opt/server
COPY requirements.txt .
COPY payment.ini .
COPY *.py .
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
    && chown -R roboshop:roboshop /opt/server
RUN pip3 install -r requirements.txt
CMD ["uwsgi", "--ini", "payment.ini"]





# FROM python:3.9.23-alpine3.22 AS builder
# WORKDIR /opt/server
# RUN apk add --no-cache \
#     build-base \
#     linux-headers \
#     musl-dev \
#     python3-dev \
#     libffi-dev \
#     gcc
# COPY requirements.txt .
# RUN pip3 install -r requirements.txt
# COPY *.py .
# COPY payment.ini .


# FROM python:3.9.23-alpine3.22
# WORKDIR /opt/server
# RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
#     && chown -R roboshop:roboshop /opt/server
# COPY --from=builder /opt/server /opt/server
# USER roboshop
# CMD ["uwsgi", "--ini", "payment.ini"]




# FROM python:3.9
# EXPOSE 8080
# WORKDIR /opt/server
# COPY requirements.txt .
# COPY *.py .
# COPY payment.ini .
# RUN pip3 install -r requirements.txt
# CMD ["uwsgi", "--ini", "payment.ini"]
