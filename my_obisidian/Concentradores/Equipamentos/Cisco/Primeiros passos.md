



***Comandos básicos:***
- Salvar na memória permanente (impede que perca as configurações após reiniciado): `write memory`
- Exibir todas as configurações atuais: ``show running-config full``





------------------------------------------------------------
***Configurando interface***
`enable`
`configure terminal`
`interface nome_interface`

- Já dentro da interface vamos utilizar o primeiro comando para ativar a interface: `no shutdown`
- Podemos configurar um endereço IP da seguinte forma: `ìp address 102.168.1.1 255.255.255.0`	
- Para configurar dinâmico é bem simples: ``ip address dhcp``
- Para checar as configurações das interfaces podemos utilizar:``show ip interface brief``











------------------------------------------------------------
***Criando usuário e liberando TELNET***

`enable`
`configure terminal`

- Para configurar Telnet, entre no modo de configuração de linha VTY:
`line vty 0 4`
- Defina uma senha para o acesso Telnet:
`password <SENHA>`
- Habilite o login usando a senha:
	`login`
- Definindo o limite de inatividade (Opicional):
`exec-timeout 5 0`


-------------------------------------------------------------