- Cài đặt virtualbox
- Chạy lệnh: vagrant up trong từng folder để tạo máy ảo
- Trên máy master chạy lệnh để khởi tạo node master của cluster:
     kubeadm init --apiserver-advertise-address="địa chỉ ip đã đặt cho máy master" --pod-network-cidr=192.168.0.0/16
- Chép file cấu hình đảm bảo kubectl trên máy master kết nối đến cluster:
     <space>mkdir -p /root/.kube<space>
     <space>sudo cp -i /etc/kubernetes/admin.conf /root/.kube/config<space>
     <space>sudo chown $(id -u):$(id -g) /root/.kube/config<space>
- Cài đặt pod network plugin: để các pod giao tiếp với nhau trong k8s cluster:
     <space>https://docs.tigera.io/calico/latest/getting-started/kubernetes/self-managed-onprem/onpremises<space>
- Trên máy master lấy lệnh kết nối vào cluster:
     <space>kubeadm token create --print-join-command<space>
- Trên các máy worker chạy lệnh được in ra sau khi chạy lệnh bên trên để kết nối  các worker với cluster
