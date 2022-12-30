# DNS Slave
* Configurando a interface de rede com o netplan 
  * ``$ sudo nano /etc/netplan/00-installer-config.yaml`` 
<p><center> Figura 1: Configurando a interface de rede com o netplan </center></p>
<img src="figures/DNSslave/image7.png" alt=""
     title="Figura 1: Configurando a interface de rede com o netplan" width="1000" height="auto"/></br>


* Instalando servidor DNS secundário (slave)
  * ``$ sudo apt-get install bind9 dnsutils bind9-doc -y``
<p><center> Figura 2: Instalando servidor DNS secundário (slave) </center></p>
<img src="figures/DNSslave/image6.png" alt=""
     title="Figura 2: Instalando servidor DNS secundário (slave)" width="1000" height="auto"/></br>

* Verificando status do serviço
  * ``$ sudo systemctl status bind9``
<p><center> Figura 3: Verificando status do serviço </center></p>
<img src="figures/DNSslave/image1.png" alt=""
     title="Figura 3: Verificando status do serviço" width="1000" height="auto"/></br>

* Configurando as zonas
  * Editando arquivo ``/etc/bind/named.conf.local``
  * ``$ sudo nano /etc/bind/named.conf.local``
<p><center> Figura 4: Editando arquivo /etc/bind/named.conf.local </center></p>
<img src="figures/DNSslave/image5.png" alt=""
     title="Figura 4: Editando arquivo /etc/bind/named.conf.local" width="1000" height="auto"/></br>

* Verificando status 
<p><center> Figura 5: Verificando o status </center></p>
<img src="figures/DNSslave/image3.png" alt=""
     title="Figura 5: Verificando o status" width="1000" height="auto"/></br>

* Fazendo os testes
<p><center> Figura 6: Fazendo os testes </center></p>
<img src="figures/DNSslave/image3.png" alt=""
     title="Figura 6: Fazendo os testes" width="1000" height="auto"/></br>

<p><center> Figura 7: Dig para ns2 </center></p>
<img src="figures/DNSslave/image2.png" alt=""
     title="Figura 7: Dig para ns2" width="1000" height="auto"/></br>

<p><center> Figura 8: Dig para www </center></p>
<img src="figures/DNSslave/image4.png" alt=""
     title="Figura 8: Dig para ww" width="1000" height="auto"/></br>

<p><center> Figura 9: Ping para www </center></p>
<img src="figures/DNSslave/image8.png" alt=""
     title="Figura 9: Ping para www" width="1000" height="auto"/></br>



