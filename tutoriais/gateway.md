# Gateway

* Habilitando o firewall
     * ``sudo ufw enable``

<p><center> Figura 1: Habilitando o firewall </center></p>
<img src="figures/gateway/image5.png" alt=""
     title="Figura 1: Habilitando o firewall" width="1000" height="auto"/></br>
     
* Habilitando o ssh
     * ``sudo ufw allow ssh``

<p><center> Figura 2: Habilitando o ssh </center></p>
<img src="figures/gateway/image7.png" alt=""
     title="Figura 2: Habilitando o ssh" width="1000" height="auto"/></br>

* Configurando o arquivo ``/etc/ufw/sysctl.conf``
     * ``sudo nano  /etc/ufw/sysctl.conf``
<p><center> Figura 3: Configurando o arquivo /etc/ufw/sysctl.conf </center></p>
<img src="figures/gateway/image19.png" alt=""
     title="Figura 3: Configurando o arquivo /etc/ufw/sysctl.conf" width="1000" height="auto"/></br>

* Descomentando a linha ``net/ipv4/ip_forwarding=1``  para permitir o transporte de pacotes entre as interfaces WAN e LAN
<p><center> Figura 4: Descomentando a linha net/ipv4/ip_forwarding=1 </center></p>
<img src="figures/gateway/image8.png" alt=""
     title="Figura 4: Descomentando a linha net/ipv4/ip_forwarding=1" width="1000" height="auto"/></br>

* Conferindo as interfaces de rede 
     * ``ifconfig -a``
<p><center> Figura 5: Conferindo as interfaces de rede </center></p>
<img src="figures/gateway/image15.png" alt=""
     title="Figura 5: Conferindo as interfaces de rede" width="1000" height="auto"/></br>

* Configurando as interfaces de rede
     * ``ls -la /etc/netplan/`` para procurar o arquivo .yaml configurável
<p><center> Figura 6: Configurando as interfaces de rede </center></p>
<img src="figures/gateway/image17.png" alt=""
     title="Figura 6: Configurando as interfaces de rede" width="1000" height="auto"/></br>

* ``sudo nano /etc/netplan/00-installer-config.yaml``
<p><center> Figura 7: sudo nano /etc/netplan/00-installer-config.yaml </center></p>
<img src="figures/gateway/image1.png" alt=""
     title="Figura 7: sudo nano /etc/netplan/00-installer-config.yaml" width="1000" height="auto"/></br>

<p><center> Figura 8:  arquivo sudo nano /etc/netplan/00-installer-config.yaml </center></p>
<img src="figures/gateway/image13.png" alt=""
     title="Figura 8:  arquivo sudo nano /etc/netplan/00-installer-config.yaml" width="1000" height="auto"/></br>

* ``sudo netplan apply`` para salvar as alterações
<p><center> Figura 9: sudo netplan apply</center></p>
<img src="figures/gateway/image11.png" alt=""
     title="Figura 9: sudo netplan apply" width="1000" height="auto"/></br>

* Criando o arquivo ``/etc/rc.local`` 
     * ``sudo vi /etc/rc.local``
<p><center> Figura 10: Criando o arquivo /etc/rc.local</center></p>
<img src="figures/gateway/image3.png" alt=""
     title="Figura 10: Criando o arquivo /etc/rc.local" width="1000" height="auto"/></br>

<p><center> Figura 11: Arquivo criado</center></p>
<img src="figures/gateway/image6.png" alt=""
     title="Figura 11: Arquivo criado /etc/rc.local" width="1000" height="auto"/></br>

* Adicionando script 
<p><center> Figura 12: Adicionando script</center></p>
<img src="figures/gateway/image9.png" alt=""
     title="Figura 12: Adicionando script" width="1000" height="auto"/></br>

* Reiniciando 
     * ``sudo reboot``
<p><center> Figura 13: Reiniciando</center></p>
<img src="figures/gateway/image4.png" alt=""
     title="Figura 13: Reiniciando" width="1000" height="auto"/></br>

* Permissão de execução do arquivo
     * ``sudo chmod 775 /etc/rc.local``
<p><center> Figura 14: Permissão de execução do arquivo</center></p>
<img src="figures/gateway/image2.png" alt=""
     title="Figura 14: Permissão de execução do arquivo" width="1000" height="auto"/></br>

* Verificar status do firewall
     * ``sudo ufw status``
<p><center> Figura 15: Verificar status do firewall</center></p>
<img src="figures/gateway/image14.png" alt=""
     title="Figura 15: Verificar status do firewall" width="1000" height="auto"/></br>

* Corrigindo as informações do script 
#### Trocando a interface enp0s3 pela ens160
<p><center> Figura 16: Trocando a interface enp0s3 pela ens160</center></p>
<img src="figures/gateway/image18.png" alt=""
     title="Figura 16: Trocando a interface enp0s3 pela ens160" width="1000" height="auto"/></br>

#### Trocando a interface enp0s8 pela ens192
<p><center> Figura 17: Trocando a interface enp0s8 pela ens192</center></p>
<img src="figures/gateway/image10.png" alt=""
     title="Figura 17: Trocando a interface enp0s8 pela ens192" width="1000" height="auto"/></br>

#### Trocando o endereço IP para o IP do SAMBA
<p><center> Figura 18:Trocando o endereço IP para o IP do SAMBA</center></p>
<img src="figures/gateway/image16.png" alt=""
     title="Figura 18: Trocando o endereço IP para o IP do SAMBA" width="1000" height="auto"/></br>

#### Trocando o endereço IP para o IP do nameserver1
<p><center> Figura 19: Trocando o endereço IP para o IP do nameserver1</center></p>
<img src="figures/gateway/image12.png" alt=""
     title="Figura 19: Trocando o endereço IP para o IP do nameserver1" width="1000" height="auto"/></br>


