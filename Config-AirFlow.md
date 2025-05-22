
# 🧱 Guia Simplificado de Instalação do Apache Airflow no Linux

## Separar ambientes com máquinas virtuais e Docker:

É uma boa prática isolar os ambientes de desenvolvimento para evitar conflitos entre diferentes projetos. Imagine que você tem dois projetos: um usa o Python 3.9 e outro o Python 3.11 — se estiver tudo misturado no mesmo sistema, pode dar erro.

Por isso, usamos soluções como:

Ambientes virtuais (virtualenv): criam “mini ambientes” Python independentes, com suas próprias bibliotecas.

Máquinas virtuais (VMs): simulam um sistema inteiro dentro do seu sistema.

Docker: empacota seu projeto e tudo que ele precisa para funcionar, garantindo que ele rode igual em qualquer máquina.

Neste projeto, usaremos ambiente virtual (virtualenv), que já resolve grande parte dos problemas de isolamento em projetos Python.

---

## 2. Preparar o Sistema

**Atualize os pacotes e adicione suporte ao Python 3.9:**

```bash
sudo apt update && sudo apt upgrade -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt install python3.9 python3.9-venv -y
```

**Verifique se o Python 3.9 foi instalado corretamente:**

```bash
python3.9 --version
```

---

## 3. Criar Ambiente de Trabalho com Virtualenv

**Crie e acesse uma pasta para o projeto:**

```bash
cd ~/Documents
mkdir airflowalura && cd airflowalura
```

**Crie o ambiente virtual e ative-o:**

```bash
python3.9 -m venv venv
source venv/bin/activate
```

> Agora, todos os pacotes que você instalar ficarão restritos ao seu projeto.

---

## 4. Instalar o Apache Airflow

**Com o ambiente ativado, instale o Airflow com as dependências corretas:**

```bash
pip install 'apache-airflow==2.3.2' --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.3.2/constraints-3.9.txt"
```

**Defina a variável de ambiente que indica a pasta principal do Airflow:**

```bash
export AIRFLOW_HOME=~/Documents/airflowalura
```

**Inicie o Airflow em modo standalone (uso local):**

```bash
airflow standalone
```

> Após alguns instantes, o terminal exibirá o login (admin) e a senha gerada automaticamente. Copie a senha.

---

## 5. Acesse o Airflow via Navegador

Abra seu navegador e acesse:  
[http://localhost:8080](http://localhost:8080)  

Use o login `admin` e a senha gerada no terminal.

---

## ✅🔐  Acessar o Airflow no navegador:


Após rodar o comando airflow standalone, o terminal irá exibir um usuário (admin) e uma senha gerada automaticamente.
Essas credenciais são necessárias para acessar a interface web do Airflow, que estará disponível no seu navegador, no endereço:

arduino
Copy
Edit
http://localhost:8080
Abra esse link no navegador, insira o usuário admin e cole a senha que apareceu no terminal. Essa interface visual permite gerenciar suas tarefas (DAGs) de forma prática, como em um painel de controle.

---

Quando queremos executar o Airflow, nós temos a opção de executar cada um de seus componentes de forma separada, inicializando o banco de dados do Airflow, executando o scheduler e o webserver. Tudo de forma manual. No entanto, também temos a opção de utilizar o comando:

airflow standaloneCopiar código
Esse comando já faz tudo de forma mais automática, ou seja, inicia o banco de dados padrão do airflow, cria um novo usuário e inicia os serviços principais (o webserver e o scheduler).


```python
# Airflow needs a home. `~/airflow` is the default, but you can put it
# somewhere else if you prefer (optional)
export AIRFLOW_HOME=~/airflow

# Install Airflow using the constraints file
AIRFLOW_VERSION=2.3.2
PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)"
# For example: 3.7
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"
# For example: https://raw.githubusercontent.com/apache/airflow/constraints-2.3.2/constraints-3.7.txt
pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"

# The Standalone command will initialise the database, make a user,
# and start all components for you.
airflow standalone

# Visit localhost:8080 in the browser and use the admin account details
# shown on the terminal to login.
# Enable the example_bash_operator dag in the home page

```