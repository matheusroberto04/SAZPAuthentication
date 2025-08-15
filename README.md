# 🔐 Django OAuth 2.0 Authentication

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-4.x-green)](https://www.djangoproject.com/)
[![OAuth 2.0](https://img.shields.io/badge/OAuth-2.0-orange)](https://oauth.net/2/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

Sistema de autenticação seguro desenvolvido com **Django** e suporte a **OAuth 2.0**, permitindo login com provedores externos como **Google**, **GitHub** ou outros.  
Ideal para aplicações que exigem **login social** e gerenciamento de usuários de forma simplificada.

---

## 🚀 Tecnologias utilizadas
- **Python 3.10+**
- **Django 4.x**
- **django-allauth** (para integração com OAuth 2.0)
- **SQLite3** (banco de dados padrão — pode ser substituído por PostgreSQL/MySQL)

---

## 📦 Pré-requisitos
- [Python 3.10 ou 3.11](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/)
- Conta e credenciais no provedor OAuth desejado (Google, GitHub, etc.)

---
## ⚙️ Instalação e configuração

### 1️⃣ Clonar o repositório

`git clone https://github.com/seu-usuario/django-oauth-auth.git`

`cd django-oauth-auth`

### 2️⃣ Criar e ativar o ambiente virtual

Instale primeiro o módulo da virtualenv com o seguinte comando:

`pip install virtualenv`

Depois crie a virtualenv e dê um nome para ela ( nome padrão é venv)

`python -m virtualenv .venv`

# Windows (PowerShell)

`.venv\Scripts\Activate.ps1`

# Linux/Mac

`source .venv/bin/activate`

### 3️⃣ Instalar dependências

Para instalar as dependências use o seguinte comando:

`pip install -r requirements.txt`

### 4️⃣ Configurar credenciais OAuth

- Vá até o site do provedor (Google Developers, GitHub Developer, etc.).

- Crie um OAuth Client ID.

- Adicione o Redirect URI:

`http://127.0.0.1:8000/accounts/google/login/callback/`

(Troque google pelo provedor que estiver configurando)

No arquivo settings.py, adicione:

`SOCIAL_AUTH_GOOGLE_OAUTH2_KEY=SEU_CLIENT_ID`

`SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET=SUA_CLIENT_SECRET`

Caso tenha duvidas em como conseguir seu CLIENT ID e seu CLIENTE SECRET basta pedir ajuda a uma IA ( ChatGpt ) para que ele forneça as informações necessárias, pois cada provedor tem uma maneira diferente de conseguir suas chaves!

### 5️⃣ Aplicar migrations

`python manage.py migrate`

### 6️⃣ Criar superusuário (opcional)

Caso você queira acessar a parte de adminstração django precisa criar um superuser usando o comando:

`python manage.py createsuperuser`

### 7️⃣ Rodar o servidor

Depois é só rodar o servidor usando o comando:

`python manage.py runserver`

🔑 Fluxo de autenticação

1. Usuário acessa a página de login.

2. Seleciona o provedor OAuth (ex.: Google).

3. É redirecionado para autenticação no provedor.

4. Ao confirmar, retorna para o site com a sessão ativa.

### Agradecimentos

Espero que goste, é um projeto simples mas onde depositei uma parte de meu tempo para desenvolve-lo e entender cada parte do código!
