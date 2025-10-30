# 🚀 Criar e Publicar Repositório Local no GitHub via SSH

Guia completo para transformar a pasta **condo-saas-pro** em um repositório Git e publicá-lo no GitHub usando SSH.

---

## 🧩 1. Entrar na pasta do projeto

```bash
cd ~/caminho/para/condo-saas-pro
```

---

## 🧰 2. Inicializar o repositório Git

```bash
git init
```

Isso cria uma pasta oculta `.git` que armazenará o histórico e as configurações do repositório.

---

## 📦 3. Adicionar todos os arquivos do projeto

```bash
git add .
```

---

## 🧾 4. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit: estrutura inicial do projeto condo-saas-pro"
```

---

## 🌐 5. Adicionar o repositório remoto no GitHub

O repositório remoto já existe e usa SSH no seguinte endereço:

```bash
git remote add origin git@github.com:cloud4u-net/condo-saas-pro.git
```

Verifique se foi adicionado corretamente:

```bash
git remote -v
```

Saída esperada:
```
origin  git@github.com:cloud4u-net/condo-saas-pro.git (fetch)
origin  git@github.com:cloud4u-net/condo-saas-pro.git (push)
```

---

## 🚀 6. Enviar o código para o GitHub

```bash
git branch -M main
git push -u origin main
```

Após isso, seu projeto estará publicado em:

👉 https://github.com/cloud4u-net/condo-saas-pro

---

## 🧠 7. Comandos úteis no dia a dia

- Ver status das alterações:
  ```bash
  git status
  ```

- Adicionar e enviar novas alterações:
  ```bash
  git add .
  git commit -m "mensagem do commit"
  git push
  ```

- Atualizar o repositório local com mudanças remotas:
  ```bash
  git pull
  ```

---

**Autor:** Jorge Alberto  
**Projeto:** condo-saas-pro  
**Licença:** MIT  
**Data:** Outubro/2025  
