## Atualização do sistema

Logo após a instalação, a primeira coisa que se deve fazer é atualizar o sistema. Lembre-se que esta pode ser uma tarefa demorada por causa da quantidade de dados que o Fedora irá baixar.

```
sudo dnf update
```

## Instalação das ferramentas de desenvolvedor

Utilize este comando para instalar os pacotes necessários para desenvolvimento no Fedora. Muitos deles servirão para compilar pacotes e evitarão futuras dores de cabeça.

```
sudo dnf groupinstall 'Development Tools' && dnf groupinstall 'C Development Tools and Libraries'
```

## Ative o repositório do RPM Fusion

Os repositórios RPM Fusion são importantes para instalar pacotes extras free e non-free que não constam no repositório padrão do Fedora.

```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

Atualize seu sistema após a instalação do mesmo (sudo dnf update).

##  Instalação do Fedy

O Fedy é um programa criado para a instalação automatizada de softwares que o Fedora não distribui nos seus repositórios, como por exemplo, suporte para MP3, Adobe Flash, Oracle Java, temas, entre outros, com apenas alguns cliques.

A instalação original do Fedy (com base no pacote pré-compilado) não funcionou. Portanto, para garantir, é melhor compilar o pacote manualmente:

```
git clone https://github.com/folkswithhats/fedy
cd fedy
sudo make install
```

## Programas essenciais

Após a configuração inicial do Fedora, partiremos para a instalação dos programas mais utilizados no dia a dia.

#### Gnome Tweak
