# Verifique qual o alias com o lsusb
lsusb

De acordo com o alias, vc deverá baixar o driver correto nas listas abaixo.

Baixar o arquivo .deb e passar para um pendrive

# Atualizar o arquivo /etc/apt/sources.list

`sudo nano /etc/apt/sources.list`

Deixá-lo desta forma:

![image](https://github.com/Easyfood/nutrebem-terminal-linux/assets/10848224/33922cc2-08b4-42d7-8467-d2d05699c5e3)

# Atualizar a distro
`sudo apt-get clean`

`cd /var/lib/apt`

`sudo mv lists lists.old`

`sudo mkdir -p lists/partial`

`sudo apt-get clean`

`sudo apt-get update`

`sudo apt-cache search linux-image`

`sudo apt install linux-image-3.16.0-6-686-pae`

`sudo reboot now`

# Baixar todas as dependências necessárias para instalação das antenas

`uname -r`

`sudo apt-get install linux-headers-` (coloque aqui o resultado do `uname -r`)

`sudo apt-get install gcc-4.8 git build-essential`

`git clone https://github.com/Easyfood/terminal_antenas.git`

# Avalie a família da antena que usará e siga os seguintes passos
 
##  Família: 2357:XXXX

`cd rtl8192eu`

`make clean`

`sudo make`

`sudo make all`

`sudo make install`

`sudo modprobe 8192eu`

`sudo reboot now`

## Família: https://wiki.debian.org/rtl819x#r8188eu

`cd rtl8188eu`

`make all`

`sudo make install`

`sudo modprobe 8188eu`

`sudo reboot now`

## Família: 148f:7601

`cd mt7601usta/src `

`make`

`sudo make install`

`sudo mkdir -p /etc/Wireless/RT2870STA/`

`sudo cp RT2870STA.dat /etc/Wireless/RT2870STA/`

`sudo modprobe mt7601Usta`

`sudo reboot now`

# Conclusão da instalação
