Comando úteis:
<mark class="hltr-r">Verificar IP Público:</mark>
<span style="font-size: 14px; font-family:monospace">curl ifconfig.me</span>
-------------------------
<mark class="hltr-r">Tabela de roteamento:</mark>
<span style="font-size: 14px; font-family:monospace">route -n</span>
-------------------------
<mark class="hltr-r">Advanced port scanner for linux:</mark>
<span style="font-size: 14px; font-family:monospace">nmap {IP} [-P] [port]</span>
-------------------------
<mark class="hltr-r">Transferência de arquivo entre servidores:</mark>
<span style="font-size: 14px; font-family:monospace">scp {user}@{ip_address}:/caminho_do_arquivo caminho_para_onde_a_maquina_vai_salvar</span>
--------------------------
Caminhos úteis:
<mark class="hltr-r">Lista principais parâmetros do IXC como por exemplo alguns logins:</mark>
<span style="font-size: 14px; font-family:monospace">/var/www/includes/ixc_parametros.php </span>
-------------------------
<mark class="hltr-r">Dados da conexão do radius com banco de dados</mark>
<span style="font-size: 14px; font-family:monospace">/etc/freeradius/3.0/mods-enabled/sql</span>
-------------------------
<mark class="hltr-r">Ferramenta de capturar pacotes na rede do linux</mark>
<span style="font-size: 14px; font-family:monospace">sudo tcpdump -i {nome_interface}</span>
<span style="font-size: 14px; font-family:monospace">sudo tcpdump -i {nome_interface} -w {nome_arquivo}.{cap/pcap}</span> (Salva um arquivo no diretório atual)

<mark class="hltr-r">Comando para inicializar serviços juntos com o boot da máquina</mark>
<span style="font-size: 14px; font-family:monospace">systemctl enable nome_do_servico.service</span>


<mark class="hltr-r">Reiniciar uma interface</mark>
<span style="font-size: 14px; font-family:monospace">sudo ifdown nome_interface</span>
<span style="font-size: 14px; font-family:monospace">sudo ifup
nome_interface</span>


sudo usermod -aG sudo <nome_do_usuario>



ssh -o KexAlgorithms=+diffie-hellman-group1-sha1 -o KexAlgorithms=+diffie-hellman-group14-sha1 admin@192.168.20.2

