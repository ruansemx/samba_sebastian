<h1 align="center">Samba_Sebastian</h1>
<h2 align="center">Configurções para criar um servidor SAMBA</h2>

<p align="center">
<b>Este Repositório Está Sendo Utilizado Somenete Para a Aplicação da Atividade Do Projeto Final da Cadeira de Segurança em Sietemas Operacionais e Redes de Computadores!</b>
</p>

<h2> 👨‍💻 Objetivos Da Atividade</h2>
O objetivo desta atividade é que você instale e configure o Samba para compartilhar arquivos de forma segura, fazendo um controle de acesso para que cada usuário possa acessar apenas os arquivos que pertencem a ele ou os que são públicos.

<h2> 🤓 Pré-Requisitos</h2>

Para a realização dessa atividade, será necessário alguns pré-requisitos:

- Ter o virtualizador de Sistemas Operacionais VirtualBox instalado
    - [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- O Sistema Operacaional Linux Ubuntu
    - [Ubuntu 22.04.5 LTS (Jammy Jellyfish)](https://releases.ubuntu.com/jammy/ubuntu-22.04.5-desktop-amd64.iso)
 
<h2>  🦵 Passo a passo</h2>
Para iniciar, é necessário estar logado em um perfil de administrador em uma máquina virtual com o sistema operacional Ubuntu 22.04.5 que servirá como o servidor Samba. Com isso, certifique-se que as configurações da sua placa de rede esteja conforme apresentado abaixo:

<img src="images/img1.png" width="500px;" alt="imagem 1"/>

Agora você deve estar vendo uma janela parecida com a da figura abaixo. Faça as modificações necessárias prestando atenção nos campos indicados na figura abaixo.

<img src="images/img2.png" width="500px;" alt="imagem 2"/>

Após realizar as modificações, clique em Ok.

<h3>  💻 Instalação dos programas</h3>
Para dar continuidade, é preciso instalar a ferramenta Samba para a criação do servidor e o editor de texto Vim. Com o prompt de comando aberto, digite o comando a seguir e ponha a sua senha de administrador. A partir disso, seus comandos terão permissão de administrador:

```bash
~$ sudo su
```

Instale o Samba e o Vim:
```bash
~#  apt install samba
~#  apt install vim
```

Agora verifique o status do servidor Samba:
```bash
~#  systemctl status smbd
```

resultado:

<img src="images/img3.png" width="500px;" alt="imagem 3"/>

Agora verifique o status do servidor nmbd que é um programa que atua como um servidor de nome de serviço NetBIOS e daemon de navegação do Samba.

```bash
~#  systemctl status nmbd
```

O resultado deve ser:

<img src="images/img4.png" width="500px;" alt="imagem 4"/>

<h3>  📁 Criação dos usuários e pastas a serem compartilhadas</h3>
Vá para o diretório /home:

```bash
~# cd /home
```

Crie as pastas si e ads para serem compartilhadas entre alunos de cada curso:

```bash
~# mkdir si
~# mkdir ads
```

