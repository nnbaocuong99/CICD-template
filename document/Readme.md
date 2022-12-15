### usage
---

1. Tạo Master VM chạy rancher image:
- cài đặt: `vagrant up`



2. Tạo worker VM cài đặt cluster:
- copy Vagrantfile-worker ra thư mục và đổi tên thành Vagrantfile
- cài đặt: vagrant up



3. Chạy rancher image trên master VM:
- SSH vào master VM
- kiểm tra docker đã cài đặt hay chưa: `docker version`
- `docker run -d --name=rancher-server --restart=unless-stopped -p 80:80 -p 443:443 --privileged rancher/rancher:v2.7`
- truy cập rancher UI: `IP`



4. Tạo cluster trên worker VM:
- truy cập rancher UI
- add --address worker_IP
