# Khái niệm về Docker Image
Docker image là một ảnh của một môi trường phát triển (có thể hiểu là snapshot). Nói ngắn gọn là chúng ta có thể gói các cài đặt môi trường (OS, package, phần mềm của chúng ta đã viết, …) lại thành 1 cục duy nhất, đó chính là docker image. Khi đã có docker image, ta có thể khởi tạo các docker container từ docker image.

* Nâng cao của docker image là dockerfile. Trong đó dockerfile là chứa 1 kịch bản được viết sẵn của các docker image tổng hợp lại (muốn biết thêm về dockerfile thì xem thêm tại :) 

# lệnh cơ bản bền docker image
```
docker image
```
xem các image đang có trên local

```
docker search centos
```
Tìm kiếm các image liên quan đến centos, nếu cần tìm image nào thì thay "centos" bằng cái mong muốn

```
docker image ls
```
List ra các image đang có trên máy local
```
sudo docker rmi [Image ID]
```
chỉ định xóa image
```
docker pull centos:7
```
Đẩy image từ local lên dockerhub
```
docker commit -m "Comment" -a "Tác giả"  [Container ID] [Image Name]
docker commit -m "Centos Project01" -a "Nguyen Hoang Giang" d452f1a1b69d giangnh/project01:v1
```
tạo, xác thực image để đẩy lên dockerhub
