ACESSO:


**Comandos de Rotina:**
<mark class="hltr-r">Informações importantes sobre a conexão do cliente:</mark>
<span style="font-size: 14px; font-family:monospace">display access-user username {login_client} verbose</span>
<mark class="hltr-r">Desconectar o cliente</mark>
<span style="font-size: 14px; font-family:monospace">entre em: system-view  
dentro de system-view entre em: aaa  
digite: cut access-user username {login_client} all
</span>
<span style="font-size: 14px; font-family:monospace">cut access-user username 01170 all</span>
<mark class="hltr-r">Motivo da desconexão:</mark>
<span style="font-size: 14px; font-family:monospace">display aaa offline-record username treinamento</span>
<mark class="hltr-r">Alterar porta SSH:</mark>
<span style="font-size: 14px; font-family:monospace">ssh server port {new_port}</span>
<mark class="hltr-r">Debugging avançado:</mark>
<span style="font-size: 14px; font-family:monospace">debugging radius packet
</span>
<span style="font-size: 14px; font-family:monospace">terminal debugging</span>
<span style="font-size: 14px; font-family:monospace">terminal monitor</span>
-----Desligar Debbuging-----
<span style="font-size: 14px; font-family:monospace">undo debugging all</span>
<span style="font-size: 14px; font-family:monospace">undo terminal
</span>
<span style="font-size: 14px; font-family:monospace">undo terminal monitor
</span>

<mark class="hltr-r">Log de falhas de autenticação:</mark>
<span style="font-size: 14px; font-family:monospace">aaa online-fail-record brief</span>




FORMA CORRETA DOMAIN RADIUS:


radius-server group ixcprovedor
 radius-server shared-key-cipher %^%#vLog=&)}q=n2P:*r9}2>GT8EHO`sr4$5iU:gFuV2%^%#
 radius-server shared-key-cipher %^%#oeC|9v9nb1FH%(4nGnPFAq;wT83g.5Q)6&.tM"F:%^%# authentication 45.230.225.155 source ip-address 45.230.224.6 1812 weight 0
 radius-server shared-key-cipher %^%#0yGE~_HyiOVa~RA3Cni,XK)o1G@l5MoHZ.1FW|}4%^%# accounting 45.230.225.155 source ip-address 45.230.224.6 1813 weight 0
 radius-server source interface LoopBack0
 radius-server attribute translate
 radius-server user-name original
 radius-server user-name trust-server-request 
 radius-attribute include HW-Auth-Type
 radius-attribute include Reply-Message coa-nak
 radius-attribute include edsg-service-name accounting-request
 radius-attribute include Event-Timestamp accounting-on accounting-off 
 radius-attribute include NAS-Port-Id
 radius-server nas-port-id include ce-vlan delimiter - pe-vlan delimiter - interface-description
 radius-attribute disable CISCO-AVPair receive
 radius-attribute translate extend HW-Auth-Type vendor-specific 2011 109 access-request account 
 radius-attribute assign hw-mng-ipv6 pppoe motm 
 radius-attribute case-sensitive qos-profile-name
 radius-attribute apply user-name match user-type ipoe
 radius-attribute apply framed-ipv6-pool match pool-type
 radius-attribute service-type value outbound user-type ipoe 
 radius-attribute hw-user-password simple coa-request
#
radius local-ip 45.230.224.6
radius local-ip all
radius-server authorization 45.230.225.135 destination-port 3799 shared-key-cipher %^%#qS|EID;oC2l4tT>O*k%-W;]%QZ\Mr&u91b"X-iuH%^%# server-group topsapp
radius-server authorization 45.230.225.155 destination-port 3799 shared-key-cipher %^%#JnJ$IhG\.S8zuIH^J%c*{d|RBu^-a)/du`:(qUJ&%^%# server-group ixcprovedor
#

