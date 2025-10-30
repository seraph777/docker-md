# 🔑 Configuração de Chave SSH para GitHub

Guia passo a passo para criar, configurar e usar chaves SSH com o GitHub, permitindo clonar repositórios de forma segura e sem precisar digitar senha.

---

## 🧰 1. Verificar se já existe uma chave SSH

```bash
ls -al ~/.ssh
```

Se aparecerem arquivos como `id_rsa` e `id_rsa.pub` ou `id_ed25519` e `id_ed25519.pub`, você já possui uma chave configurada.

---

## 🔑 2. Gerar uma nova chave SSH

### Recomendado (Ed25519):
```bash
ssh-keygen -t ed25519 -C "seu_email@exemplo.com"
```

### Alternativo (RSA 4096 bits):
```bash
ssh-keygen -t rsa -b 4096 -C "seu_email@exemplo.com"
```

Durante o processo:
- Pressione **Enter** para aceitar o local padrão (`~/.ssh/id_ed25519`);
- Opcional: insira uma **passphrase** para mais segurança.

---

## 🧠 3. Iniciar o agente SSH e adicionar a chave

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Ou, se for RSA:

```bash
ssh-add ~/.ssh/id_rsa
```

---

## 📋 4. Copiar a chave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie o conteúdo exibido (começa com `ssh-ed25519` e termina com seu e-mail).

---

## 🧩 5. Adicionar a chave no GitHub

1. Acesse: [GitHub → Settings → SSH and GPG keys](https://github.com/settings/keys)
2. Clique em **New SSH key**
3. Cole o conteúdo da sua chave pública
4. Nomeie (ex: “Notebook-Trabalho”)
5. Salve

---

## 🧪 6. Testar a conexão

```bash
ssh -T git@github.com
```

Se tudo estiver certo:
```
Hi jorgealberto! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## 🧬 7. Clonar repositórios via SSH

```bash
git clone git@github.com:usuario/repositorio.git
```

---

## ⚙️ 8. Configuração global do Git (opcional)

```bash
git config --global user.name "Jorge Alberto"
git config --global user.email "seu_email@exemplo.com"
```

---

**Autor:** Jorge Alberto  
**Licença:** MIT  
**Data:** Outubro/2025  
