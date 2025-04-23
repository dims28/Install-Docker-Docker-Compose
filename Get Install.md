## 1. Install Docker dan Docker Compose

### Update sistem:
```bash
sudo apt update && sudo apt upgrade -y
```

###  Install dependensi:
```bash
sudo apt install ca-certificates curl gnupg lsb-release -y
```

### Tambahkan GPG Key:
```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg \
  --dearmor -o /etc/apt/keyrings/docker.gpg
```

### Tambahkan repository Docker:
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker:
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

### Cek versi Docker:
```bash
docker --version
docker compose version
```

### (Opsional) Jalankan Docker tanpa `sudo`:
```bash
sudo usermod -aG docker $USER
newgrp docker
```
