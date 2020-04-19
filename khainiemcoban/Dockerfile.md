#khái niệm về dockerfile
- Dockerfile là file config cho Docker để build ra image. Nó dùng một image cơ bản để xây dựng lớp image ban đầu. Một số image cơ bản: python, unbutu and alpine. Sau đó nếu có các lớp bổ sung thì nó được xếp chồng lên lớp cơ bản. Cuối cùng một lớp mỏng có thể được xếp chồng lên nhau trên các lớp khác trước đó.
## Các config :
* FROM — chỉ định image gốc: python, unbutu, alpine…
* LABEL — cung cấp metadata cho image. Có thể sử dụng để add thông tin maintainer. Để xem các label của images, dùng lệnh docker inspect.
* ENV — thiết lập một biến môi trường.
* RUN — Có thể tạo một lệnh khi build image. Được sử dụng để cài đặt các package vào container.
* COPY — Sao chép các file và thư mục vào container.
* ADD — Sao chép các file và thư mục vào container.
* CMD — Cung cấp một lệnh và đối số cho container thực thi. Các tham số có thể được ghi đè và chỉ có một CMD.
* WORKDIR — Thiết lập thư mục đang làm việc cho các chỉ thị khác như: RUN, CMD, ENTRYPOINT, COPY, ADD,…
* ARG — Định nghĩa giá trị biến được dùng trong lúc build image.
* ENTRYPOINT — cung cấp lệnh và đối số cho một container thực thi.
* EXPOSE — khai báo port lắng nghe của image.
* VOLUME — tạo một điểm gắn thư mục để truy cập và lưu trữ data.
VD tạo 1 dockerfile :

```
# Get base image
FROM centos:7

# Author
MAINTAINER "Nguyen Hoang Giang"

#Cai dat apache
RUN yum update -y
RUN yum install -y sudo
RUN yum install -y epel-release
RUN yum install -y http://rpms.famillecollet.com/enterpr...
RUN yum clean all
RUN yum -y install wget
RUN yum -y install httpd
RUN yum -y install --enablerepo=remi,remi-php71 php php-devel php-mbstring php-pdo php-gd php-xml php-mcrypt php-pgsql
 
#Thiet lap thu muc lam viec 
WORKDIR /var/www/html

#copy code tu thu muc code vao image
ADD ./code /var/www/html

# start httpd
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

#Cung cap cong kết noi ra ngoai
EXPOSE 80
```
