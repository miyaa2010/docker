Các lệnh với image
- Tìm image để cài đặt
docker search centos
- List các image đang có
docker image ls
- Xóa image
sudo docker rmi [Image ID]
Chú ý: Các image mà có container đang chạy thì sẽ không xóa được mà phải xóa container liên quan tới nó trước
- Pull image về
docker pull centos:7

Làm việc với container

- Chạy 1 container từ image
 docker run --privileged -d -p 80:80 [Image Name] /sbin/init
docker run --privileged -d -p 80:80 centos:7 /sbin/init

- Vào container để chạy lệnh
docker exec -it [Container ID] /bin/bash 

- Cài đặt apache
yum -y install httpd
systemctl start httpd
systemctl enable httpd

echo "Xin chào mn mình là nguyễn hoàng giang(giangnh)" > /var/www/html/index.html

- Thoát ra khỏi container
exit

- Tạo image để triển khai cho máy khác
docker commit -m "Comment" -a "Tác giả"  [Container ID] [Image Name]
docker commit -m "Centos Project01" -a "Nguyen Hoang Giang" d452f1a1b69d Nguyen Hoang Giang/project01:v1

- Đăng nhập vào docker/hub
docker login

- Đưa image lên docker hup để mọi người cùng sử dụng
docker push [Tên image]
docker push Nguyen Hoang Giang/project01:v1
 
- Check các container đang chạy
sudo docker ps -a

- Xem trạng thái container
docker container ls -a

- Xóa containner
sudo docker rm [Container ID]

- Stop container
docker container stop [Container ID]

- Restart container
docker container restart [Container ID]

- Pause container
docker container pause  [Container ID]

- Truy cập vào các container đang chạy
docker container attach [Container ID]


- Lệnh stop toàn bộ container
docker stop $(docker ps -a -q)

- Lệnh xóa toàn bộ container
docker rm $(docker ps -a -q)

- Lệnh xóa toàn bộ image
docker rmi -f $(docker images -a -q)
