# 🐳 Instalação do Docker e Docker Compose

Guia simples e direto para instalar **Docker** e **Docker Compose** em sistemas baseados em **Ubuntu/Debian**.

---

## 🔧 1. Atualizar pacotes do sistema

```bash
sudo apt update
sudo apt upgrade -y
```

---

## 📦 2. Remover versões antigas (caso existam)

```bash
sudo apt remove docker docker-engine docker.io containerd runc -y
```

---

## 🧰 3. Instalar dependências necessárias

```bash
sudo apt install ca-certificates curl gnupg lsb-release -y
```

---

## 🔑 4. Adicionar chave GPG oficial do Docker

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

---

## 🏗️ 5. Adicionar o repositório Docker

```bash
echo   "deb [arch=$(dpkg --print-architecture)   signed-by=/etc/apt/keyrings/docker.gpg]   https://download.docker.com/linux/ubuntu   $(lsb_release -cs) stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

## 📥 6. Instalar Docker Engine e Docker CLI

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

## ▶️ 7. Testar o Docker

```bash
sudo docker run hello-world
```

Se aparecer a mensagem **“Hello from Docker!”**, a instalação está correta ✅

---

## 👤 8. Permitir execução sem `sudo` (opcional)

```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

## 🧩 9. Instalar Docker Compose (plugin independente)

Verifique a versão mais recente no [GitHub oficial](https://github.com/docker/compose/releases).

Exemplo de instalação (substitua `v2.29.2` pela última versão estável):

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/v2.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

---

## ✅ 10. Verificar instalação do Docker Compose

```bash
docker-compose --version
```

Saída esperada (exemplo):

```
Docker Compose version v2.29.2
```

---

## 🧹 11. Dicas adicionais

- Iniciar Docker manualmente:  
  ```bash
  sudo systemctl start docker
  ```
- Habilitar na inicialização:  
  ```bash
  sudo systemctl enable docker
  ```

---

**Autor:** Jorge Alberto  
**Licença:** MIT  
**Data:** Outubro/2025  
