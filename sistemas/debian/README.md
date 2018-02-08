## Configuração dos repositórios

Abra o gedit em modo root (su), vá em /etc/apt/ e abra o arquivo sources.list. Retire qualquer linha
referente ao cd de instalação do Debian e adicione ao final de cada linha dos repositórios "contrib
non-free". Deve ficar algo parecido com isto:

```
deb http://ftp.br.debian.org/debian/ jessie main contrib non-free
deb-src http://ftp.br.debian.org/debian/ jessie main contrib non-free

deb http://security.debian.org/ jessie/updates main contrib non-free
deb-src http://security.debian.org/ jessie/updates main contrib non-free

# jessie-updates, previously known as ‘volatile’
deb http://ftp.br.debian.org/debian/ jessie-updates main contrib non-free
deb-src http://ftp.br.debian.org/debian/ jessie-updates main contrib non-free
```

## Instalação do Sudo

Abra o terminal em modo root (su) e execute o seguinte comando:

```
$ apt-get install sudo
```

Se aparecer o seguinte erro ao utilizar algum comando seguido do sudo: “User is not in the sudoers
file. This incident will be reported.”, execute o seguinte código:

```
$ echo 'username ALL=(ALL) ALL' >> /etc/sudoers
```

Em username, coloque o nome da conta que você quer adicionar no arquivo sudoers.

## Instalação dos drivers e pacotes essenciais

Para a instalação do python-glade2 e do build-essential (importante para compilar programas e pacotes), execute os seguintes comandos:

```
$ sudo apt-get install python-glade2
$ sudo apt-get install build-essential
```

Para a instalação do firmware da realtek, execute o seguinte comando:

```
$ sudo apt-get install firmware-realtek
```

Para a instalação do driver padrão da placa de vídeo, execute o seguinte comando:

```   
$ sudo apt-get install firmware-linux-nonfree
```

Caso apareça o seguinte erro na instalação de algum destes pacotes: “Gtk-Message: Failed to load
module “canberra-gtk-module”, execute o seguinte comando:
  
```
$ sudo apt-get install libcanberra-gtk*
```

## Driver proprietário - AMD (fglrx)

Não instalar o driver da AMD (fglrx) no Debian 8 - Jessie com a interface GNOME 3, pois a interface
gráfica não irá iniciar no próximo arranque do sistema.
Caso a instalação do Debian 8 - Jessie não seja com a interface GNOME 3, digite na barra de busca
do Synaptic: fglrx (FireGL and Radeon for X), marque para instalação o pacote fglrx-driver e outros
que você achar necessário (como por exemplo, o painel de controle da AMD, o console de erros, entre
outros.
Após a instalação dos pacotes, reinicie o pc e digite no terminal o seguinte comando para configurar
o fglrx com as configurações padrões:

```
$ sudo aticonfig --initial
```