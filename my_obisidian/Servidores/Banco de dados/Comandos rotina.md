***Acesso ao banco:***
`mysql -u {username} -p {password} -A`

-u: especificar o nome de usuário
-p: solicitar senha para o determinado usuário

-A: Não carregar informações adicionais de tabela no início, isso ajuda quando temos vários banco de dados e evita sobrecarregar o banco de dados

DICA: uma forma mais segura para acessar, por padrão, é não definir a senha diretamente na linha de código, esperar o terminal solicitar.

-------------------------------------
Ativando os logs do mariadb:

nano /etc/mysql/my.cnf

Adicione as seguintes linha:
[mysqld]
general_log = 1
general_log_file = /var/log/mysql/mysql.log

reinicie o serviço do mariadb

tail -f /var/log/mysql/mysql.log <---- Para visualizar os logs
