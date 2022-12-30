# DNS Master

* instalando o bind9
  * ``$ sudo apt-get install bind9 dnsutils bind9-doc -y``

* verificando o status do serviço
  * ``$ sudo systemctl status bind9``
  * caso não esteja ativo:
  * ``$ sudo systemctl enable bind9``

* acessar o diretório /etc/bind
  * ``$ ls /etc/bind``

* criar o diretório /etc/bind/zones
  * ``$ sudo mkdir /etc/bind/zones ``

* criar os arquivos db
  * criando o arquivo de zona direta
  * ``$ sudo cp /etc/bind/db.empty /etc/bind/zones/db.grupo1.turma914.ifalara.local``
  * criando o arquivo de zona reversa	
  * ``$ sudo cp /etc/bind/db.127 /etc/bind/zones/db.10.9.14.rev``

* editando arquivos db
  * ``$ sudo nano db.labredes.ifalarapiraca.local ``
  * ``$ sudo nano db.10.9.14.rev``

* Adicionando as zonas 
  * ``$ cd /etc/bind/zones``
  * ``$ sudo nano /etc/bind/named.conf.local``

* Verificando a sintaxe de configuração do BIND
  * ``$ sudo named-checkconf``

* Verificando a sintaxe dos arquivos db
  * ``$ sudo named-checkzone grupo1.turma914.ifalara.local db.grupo1.turma914.ifalara.local``

  * ``$ sudo named-checkzone 14.9.10.in-addr.arpa db.10.9.14.rev``

* Configurando para somente resolver endereços IPv4
  * ``$ sudo nano /etc/default/named``
  * Adicionar linha ``OPTIONS="-4 -u bind"``

* reiniciando o bind
  * ``$ sudo systemctl restart bind9``

* adicionando os name servers

  * ``$ sudo nano /etc/netplan/00-installer-config.yaml``
