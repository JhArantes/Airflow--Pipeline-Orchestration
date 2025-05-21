
# Porque usar uma Maquina Virtual??

O Airflow é construído em Python, mas contém algumas bibliotecas que só funcionam no Linux. Dessa forma, soluções alternativas para usuários(as) de Windows, como máquinas virtuais ou Docker, são necessárias para uso totalmente funcional dessa ferramenta.

Aqui no curso, nós optamos pelo uso de uma máquina virtual com o sistema Ubuntu 20.04 instalado. Nesta atividade vamos aprender como podemos realizar esse processo utilizando o VMware.

# Instalaveis 

## Instalando o VMware
Para começar, precisamos instalar um gerenciador de máquinas virtuais. VMware 
https://vmware-player.br.uptodown.com/windows/download


## Baixando o Ubuntu

Além do VMware, nós também vamos fazer o download da ISO do sistema operacional que queremos instalar dentro da nossa máquina virtual. Nesse caso, vamos criar uma máquina virtual com a versão 20.04 do sistema Ubuntu. Para baixar a ISO dessa versão, você pode clicar aqui.

https://releases.ubuntu.com/20.04/


# Instalando Pacotes e Bibliotecas 

Uma vez que temos nossa máquina virtual Ubuntu instalada, é importante atualizar os pacotes e instalar algumas bibliotecas que são essenciais para evitar futuros erros enquanto estivermos utilizando o Ubuntu.

```bash
sudo apt update
```

```bash
sudo apt install build-essential gcc make perl dkms curl tcl
```

Install Vscode in Ubuntu Software

Install Python 


# Libs

```bash
sudo apt install python3-pip -y

```

```bash
pip install pandas

```