***Configurando a conta GITHUB no GIT***

``git config --global user.name "Seu Nome"``
``git config --global user.email "seuemail@exemplo.com"``

***Gerando chave SSH e adicionando no GITHUB***

Gerando a key:
``ssh-keygen -t rsa -b 4096 -C "seuemail@exemplo.com"``

Adicionado chave ao agente ssh:
``eval "$(ssh-agent -s)"``
`ssh-add ~/.ssh/id_rsa`

Visualizar chave:
`cat ~/.ssh/id_rsa.pub`

Adicionando a chave no github:
[[config.png]]

----------------------------------------
***Lançando atualização para o Github***
``git add .``
``git commit -m "mensagem"``
`git push -u origin main`

