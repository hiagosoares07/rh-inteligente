# Rh-inteligente
Projeto de desenvolvimento para uma plataforma de recrutamento on-line para[Auto-viação](https://viacaosaojose.com.br/).

## Tecnologias

- **Back-end:** [Django](https://www.djangoproject.com/) (Python).
- **Front-end:** HTML, CSS e JavaScript.
- **Estilização:** [Tailwind CSS](https://tailwindcss.com/) e [Animate.css](https://animate.style/).
- **Banco de dados local:** SQLite.

## Requisitos

- Python 3.12 ou superior.
- Git, para clonar o repositório.

O Tailwind CSS usado nas páginas é carregado pelo CDN; não é necessário instalar Node.js/npm para executar o projeto localmente.

## Instalação e execução

Os comandos abaixo devem ser executados a partir da raiz do repositório (a pasta que contém `README.md` e a pasta `rh-smart`). O ambiente virtual e as dependências são instalados na máquina local.

### Windows (PowerShell)

1. Clone o repositório e entre na pasta do projeto:

   ```powershell
   git clone https://github.com/hiagosoares07/rh-inteligente.git
   cd rh-smart
   ```

   Se o projeto já estiver clonado, apenas abra o PowerShell na raiz do repositório.

2. Crie e ative um ambiente virtual:

   ```powershell
   py -3 -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   Caso o PowerShell bloqueie a ativação do ambiente, permita scripts apenas na sessão atual e tente novamente:

   ```powershell
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
   .\.venv\Scripts\Activate.ps1
   ```

3. Instale as dependências:

   ```powershell
   python -m pip install --upgrade pip
   python -m pip install -r requirements.txt
   ```

4. Crie o arquivo `.env` local a partir do exemplo:

   ```powershell
   Copy-Item .env_example .env
   ```

   Gere uma chave secreta:

   ```powershell
   python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
   ```

   Copie o valor gerado e edite `.env`, preenchendo `SECRET_KEY`. Para desenvolvimento local, `ALLOWED_HOSTS=127.0.0.1,localhost` é suficiente.

5. Aplique as migrações e inicie o servidor:

   ```powershell
   python rh-smart\manage.py migrate
   python rh-smart\manage.py runserver
   ```

6. Abra <http://127.0.0.1:8000/> no navegador. Para acessar a área de administração, crie um usuário administrador:

   ```powershell
   python rh-smart\manage.py createsuperuser
   ```

Usuários com acesso de equipe também podem abrir o protótipo interativo do painel em <http://127.0.0.1:8000/admin-panel/>. O switch **Modo admin**, disponível no hub e no painel, alterna entre as duas visões. As ações de edição e cadastro nessa tela são apenas demonstrativas e não alteram os dados da plataforma.

A navbar e a sidebar das duas visões reutilizam os templates em `altius/templates/components/shared/`; o modo define quais opções são exibidas, enquanto a aparência comum é mantida em `altius/static/css/shared-components.css`.

### Linux, macOS e outros Unix-like (Bash)

1. Clone o repositório e entre na pasta do projeto:

   ```bash
   git clone https://github.com/Vict0r-08/JornadaAprendizagem26s2.git
   cd JornadaAprendizagem26s2
   ```

   Se o projeto já estiver clonado, apenas abra um terminal na raiz do repositório.

2. Crie e ative um ambiente virtual:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Instale as dependências:

   ```bash
   python -m pip install --upgrade pip
   python -m pip install -r requirements.txt
   ```

4. Crie o arquivo `.env` local a partir do exemplo:

   ```bash
   cp .env_example .env
   ```

   Gere uma chave secreta:

   ```bash
   python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
   ```

   Copie o valor gerado e edite `.env`, preenchendo `SECRET_KEY`. Para desenvolvimento local, `ALLOWED_HOSTS=127.0.0.1,localhost` é suficiente.

5. Aplique as migrações e inicie o servidor:

   ```bash
   python rh-smart/manage.py migrate
   python rh-smart/manage.py runserver
   ```

6. Abra <http://127.0.0.1:8000/> no navegador. Para acessar a área de administração, crie um usuário administrador:

   ```bash
   python rh-smart/manage.py createsuperuser
   ```

## Testes

Com o ambiente virtual ativado, execute a suíte de testes:

```bash
python rh-smart/manage.py test
```

Para verificar a configuração do projeto:

```bash
python rh-smart/manage.py check
```
