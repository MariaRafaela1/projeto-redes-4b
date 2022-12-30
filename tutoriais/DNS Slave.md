# DNS Slave
* Configurando a interface de rede com o netplan 
  * ``$ sudo nano /etc/netplan/00-installer-config.yaml`` 
<p><center> Figura 1: Configurando a interface de rede com o netplan </center></p>
<img src="figures/DNSslave/image7.png" alt=""
     title="Figura 1: Configurando a interface de rede com o netplan" width="1000" height="auto"/></br>


* Instalando servidor DNS secundário (slave)
  * ``$ sudo apt-get install bind9 dnsutils bind9-doc -y``


* Verificando status do serviço
  * ``$ sudo systemctl status bind9``
3

* Configurando as zonas
  * Editando arquivo ``/etc/bind/named.conf.local``
  * ``$ sudo nano /etc/bind/named.conf.local``
4

* 4.2 Verificando status 
5

* Fazendo os testes


6

7

8

9



