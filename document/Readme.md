### usage
---

1. Tạo Master VM chạy rancher image:
- copy Vagrantfile-master ra thư mục và đổi tên thành Vagrantfile
- cài đặt: vagrant up



2. Tạo worker VM cài đặt cluster:
- copy Vagrantfile-worker ra thư mục và đổi tên thành Vagrantfile
- cài đặt: vagrant up



3. Chạy rancher image trên master VM:
- SSH vào master VM
- kiểm tra docker đã cài đặt hay chưa: `docker version`
- `docker run -d --name=rancher-server --restart=unless-stopped -p 80:80 -p 443:443 --privileged rancher/rancher:v2.7-091ed163cc5c53efc50bd1a580cb4e54fa097e82-linux-amd64`
- truy cập rancher UI: `https://IP`



4. Tạo cluster trên worker VM:
- truy cập rancher UI
- cấn create cluster
- chọn kiểu custom và làm theo hướng dẫn
- khi chạy rancher agent trên worker vm thêm thuộc tính --address worker_IP
