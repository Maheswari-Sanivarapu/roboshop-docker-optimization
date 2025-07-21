FROM python:3.9.23-alpine3.22 AS builder
WORKDIR /opt/server
RUN dnf install gcc python3-devel -y
COPY requirements.txt .
RUN pip3 install -r requirements.txt
COPY *.py .
COPY payment.ini .


FROM python:3.9.23-alpine3.22
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
COPY --from=builder /opt/server /opt/server
CMD ["uwsgi", "--ini", "payment.ini"]




# FROM python:3.9
# EXPOSE 8080
# WORKDIR /opt/server
# COPY requirements.txt .
# COPY *.py .
# COPY payment.ini .
# RUN pip3 install -r requirements.txt
# CMD ["uwsgi", "--ini", "payment.ini"]
