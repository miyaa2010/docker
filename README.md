# Docker
sau đây quá trình tìm hiểu docker của Nguyễn Hoàng Giang

## khái niệm về docker 
https://github.com/hocchudong/ghichep-docker/blob/master/docs/docker-coban/ghichep-docker.md

## Cài đặt cơ bản
 ``` 
 apt-get update
 apt-get upgrade -y
 ```
 ## Cài đặt Docker
 - đăng nhập dưới quyền root để cài đặt docker :
 ```
 curl -sSL https://get.docker.com/ | sudo sh
 ```
- kết quả như sau là cài thành công
```
If you would like to use Docker as a non-root user, you should now consider
adding your user to the "docker" group with something like:

  sudo usermod -aG docker your-user

Remember that you will have to log out and back in for this to take effect!

WARNING: Adding a user to the "docker" group will grant the ability to run
         containers which can be used to obtain root privileges on the
         docker host.
         Refer to https://docs.docker.com/engine/security/security/#docker-daemon-attack-surface
```
- Thực hiện lệnh dưới để phân quyền cho user hiện tại thuộc group docker
```
 sudo usermod -aG docker `whoami`
```
- Kích hoạt docker sau khi cài đặt xong và cho phép khởi động cùng OS
```
 systemctl start docker.service
 systemctl enable docker.service
```
- Kiểm tra phiên bản của docker sau khi cài đặt, trong hướng dẫn này là bản 17.07.0-ce
```
 docker version
```

- Thử tạo container đầu tiên
```
 docker run hello-world
 ``` 
 
