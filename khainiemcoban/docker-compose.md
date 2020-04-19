# Khái niệm cơ bản về docker-compose
- Compose là công cụ giúp định nghĩa và khởi chạy multi-container Docker applications.
- Chỉ với một câu lệnh, ta có thể dễ dàng create và start toàn bộ các services phục vụ cho việc chạy ứng dụng.

- Việc sử dụng Docker Compose được tóm lược trong 3 bước cơ bản sau:
  - Khai báo app’s environment với Dockerfile.
  - Khai báo các services cần thiết để chạy app trong docker-compose.yml.
  - Run docker-compose up và Compose sẽ start và run app.

# 1. Cài đặt
- Install using pip
```sh
$ pip install docker-compose
```

Hoặc bạn có thể sử dụng cách khác: 

- Install as a container
```sh
$ curl -L https://github.com/docker/compose/releases/download/1.11.2/run.sh > /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose
```
