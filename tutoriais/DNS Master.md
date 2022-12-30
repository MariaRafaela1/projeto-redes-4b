# DNS Master

* instalando o bind9
  * ``$ sudo apt-get install bind9 dnsutils bind9-doc``
  <p><center> Figura 1: instalando o bind9 </center></p>
<img src="figures/DNSmaster/1.png" alt=""
     title="Figura 1: instalando o bind9" width="1000" height="auto"/></br>


* verificando o status do serviço
  * ``$ sudo systemctl status bind9``
  * caso não esteja ativo:
  * ``$ sudo systemctl enable bind9``
  <p><center> Figura 2: verificando o status </center></p>
<img src="figures/DNSmaster/2.png" alt=""
     title="Figura 2: verificando o status" width="1000" height="auto"/></br>


* acessar o diretório ``/etc/bind``
  * ``$ ls /etc/bind``
* criar o diretório ``/etc/bind/zones``
  * ``$ sudo mkdir /etc/bind/zones ``
  <p><center> Figura 3: criar o diretório /etc/bind/zones </center></p>
<img src="figures/DNSmaster/3.png" alt=""
     title="Figura 3: criar o diretório /etc/bind/zones" width="1000" height="auto"/></br>

* criar os arquivos db
  #### criando o arquivo de zona direta
  * ``$ sudo cp /etc/bind/db.empty /etc/bind/zones/db.grupo1.turma914.ifalara.local``
  
  <p><center> Figura 4: criando o arquivo de zona direta </center></p>
<img src="figures/DNSmaster/4.png" alt=""
     title="Figura 4: criando o arquivo de zona direta" width="1000" height="auto"/></br>

  #### criando o arquivo de zona reversa	
  * ``$ sudo cp /etc/bind/db.127 /etc/bind/zones/db.10.9.14.rev``
  <p><center> Figura 5: criando o arquivo de zona reversa </center></p>
<img src="figures/DNSmaster/5.png" alt=""
     title="Figura 5: criando o arquivo de zona reversa" width="1000" height="auto"/></br>
  
* editando arquivos db</br>
   ``$ sudo nano db.labredes.ifalarapiraca.local ``
  <p><center> Figura 6: editando arquivo db de zona direta </center></p>
<img src="figures/DNSmaster/6.png" alt=""
     title="Figura 6: editando arquivo db de zona direta" width="1000" height="auto"/></br>

   ``$ sudo nano db.10.9.14.rev``
   <p><center> Figura 7: editando arquivo db de zona reversa </center></p>
<img src="figures/DNSmaster/7.png" alt=""
     title="Figura 7: editando arquivo db de zona reversa" width="1000" height="auto"/></br>


* Adicionando as zonas 
  * ``$ cd /etc/bind/zones``
  * ``$ sudo nano /etc/bind/named.conf.local``
  <p><center> Figura 8: Adicionando as zonas</center></p>
<img src="figures/DNSmaster/8.png" alt=""
     title="Figura 8: Adicionando as zonas" width="1000" height="auto"/></br>


* Verificando a sintaxe de configuração do BIND
  * ``$ sudo named-checkconf``
  <p><center> Figura 9: Verificando a sintaxe de configuração do BIND </center></p>
<img src="figures/DNSmaster/9.png" alt=""
     title="Figura 9: Verificando a sintaxe de configuração do BIND" width="1000" height="auto"/></br>


* Verificando a sintaxe dos arquivos db
  * ``$ sudo named-checkzone grupo1.turma914.ifalara.local db.grupo1.turma914.ifalara.local``
  <p><center> Figura 10: Verificando a sintaxe do arquivo de zona direta </center></p>
<img src="figures/DNSmaster/10.png" alt=""
     title="Figura 10: Verificando a sintaxe do arquivo de zona direta" width="1000" height="auto"/></br>


  * ``$ sudo named-checkzone 14.9.10.in-addr.arpa db.10.9.14.rev``
  <p><center> Figura 11: Verificando a sintaxe do arquivo de zona reversa</center></p>
<img src="figures/DNSmaster/11.png" alt=""
     title="Figura 11: Verificando a sintaxe do arquivo de zona reversa" width="1000" height="auto"/></br>


* Configurando para somente resolver endereços IPv4
  * ``$ sudo nano /etc/default/named``
  * Adicionar linha ``OPTIONS="-4 -u bind"``
  <p><center> Figura 12:  Configurando para somente resolver endereços IPv4 </center></p>
<img src="figures/DNSmaster/12.png" alt=""
     title="Figura 12: Configurando para somente resolver endereços IPv4" width="1000" height="auto"/></br>


* reiniciando o bind
  * ``$ sudo systemctl restart bind9``
  <p><center> Figura 13: reiniciando o bind </center></p>
<img src="figures/DNSmaster/13.png" alt=""
     title="Figura 13: reiniciando o bind" width="1000" height="auto"/></br>


* adicionando os name servers

  * ``$ sudo nano /etc/netplan/00-installer-config.yaml``
  <p><center> Figura 14: adicionando os name servers </center></p>
<img src="figures/DNSmaster/14.png" alt=""
     title="Figura 14: adicionando os name servers" width="1000" height="auto"/></br>

