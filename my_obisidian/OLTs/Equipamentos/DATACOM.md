<mark class="hltr-r">Show plataform</mark> -> Para ver modelo da OLT e versão de firmware
<mark class="hltr-r">Show alarm</mark> -> alarms de onu's
<mark class="hltr-r">show firmware</mark> -> versão de firmware
<mark class="hltr-r">show tech-supporte</mark> -> show global
<mark class="hltr-r">show vlan brief -</mark>> tipos e nomes
<mark class="hltr-r">show running-config dot1q | tab</mark> -> mostrar as vlans em modo tabela e se é tagged ou untagged
<mark class="hltr-r">show interface gpon 1/1/1 onu 1 ethernet</mark> -> detalhes da interface ethernet da ONU
<mark class="hltr-r">show configuration commit list</mark> -> lista de salvamentos via commit
<mark class="hltr-r">rollback configuration</mark> -> saber os últimos possiveis roolbacks disponiveis
<mark class="hltr-r">rollback configuration valor</mark> -> volta para a posição do rollback desejado
<mark class="hltr-r">show running-config service vlan | tab</mark> -> mostrar as vlans de serviço criadas na olt e seus tipos
<mark class="hltr-r">service vlan numerovlan type 1:1</mark> -> cria uma vlan de 1 para 1, atender um cliente, ex: link dedicado
<mark class="hltr-r">service vlan numerovlan type n:1</mark> -> cria uma vlan de muitos para 1, cenário que atende residências
<mark class="hltr-r">service vlan numerovlan type tls</mark> -> transparência, quando é necessário que as onu's se comuniquem, utilizado em lan to lan, voip, matriz x filial e na vlan de gerência.
<mark class="hltr-r">dentro da pon execute: onu-enable all</mark> -> força que a ONU se anuncie novamente, ou seja, reapareça para provisionar
<mark class="hltr-r">show running-config gpon bandwidth-profile | tab</mark> -> listar em tabelas os profiles de upstream(onu->olt) e os tipos de banda criados


