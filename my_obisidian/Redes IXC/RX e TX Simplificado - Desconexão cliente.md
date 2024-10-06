
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeIk_NKtlywETrM-3RovGc4wckks0diab5yG8KBGzjjT0d_LgPphbiCkpXyawxSaNSa0CiXE3iDdt9XoXaqtBq5YuaII0fv13hxnBG4B37r4YF-Z0dKAsgG3wDECNLffrQqx4Ln6KZxWw1HTk0IM635wU5e?key=088haGOHbd6Uu7p3CTdxVA)

Sinal RX e TX

O RX e TX se referem a taxa de transmissão medida em dbm (decibéis por milliwatt), sendo que RX é o sinal que chega até determinado equipamento e o TX é o sinal que o equipamento envia.

  

RX = Reception (Receptar, receber)

TX = Transmission (Transmitir, enviar)

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcTpai4NVjoMOmmef-xmsDpghE3WsC_JFuaOZElZgj9KyMymvY0xBL87ZkSkCyQ9pFkW5ymC227MA-4ORjGF5a5E5CuSIzPjLKLSpGS-pEO61c7b2qL8BcQOL8tJGZ63brof_JmTOUR0yKkWRsALr6z3eo?key=088haGOHbd6Uu7p3CTdxVA)

  

Onde encontramos isso no cotidiano do provedor?

  

Na lógica de transmissão de luz por fibra óptica, o sinal óptico inicia no transmissor (OLT), a OLT por um exemplo transmite 4 dbm, esse valor positivo vai quebrando conforme conectores (no DIO por exemplo), distância da fibra, e as “splitagens”.

Quando a fibra chega no cliente, ela entrega um sinal RX (Recebimento) para o equipamento do cliente, geralmente entre -20dbm até no máximo -26dbm que é o indicado. Ok, podemos dizer agora que se ocorresse uma conversa entre a OLT e a ONU, apenas com valor de transmissão da OLT e o de recebimento da ONU, apenas a OLT poderia falar e a ONU apenas ouvir, seguindo essa analogia a ONU tem que falar com a OLT também, portanto a ONU tem o seu sinal de transmissão, que envia as respostas para a OLT.

  
  
  

ILUSTRAÇÃO DO TX/RX NA OLT E ONU/ONT

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcSa5cMj5LDegwaPbAqVrLtetvwR-HrZnQYW6df2xl4Zry1Ut0kOQfajjAJ7P_24POy8CU32_AS4so4Lld99KDd4aLm-zAPztATJTSX9mgB3TjkZJgzKUKmeIuRkmT20eGRTYU9gpWZ7wY91VZYG8GtaAs?key=088haGOHbd6Uu7p3CTdxVA)

  
  

ERRO DE DESCONEXÃO CLIENTES

  

Um dos erros mais comuns que os clientes relatam é o de erro ao desconectar clientes, o que geralmente é o causador disso?

  
  
  

Um passo muito importante para diagnosticar o problema, é verificar a comunicação entre o servidor e o concentrador.

  
  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdcOYpXQ8_FyQ_GTFA2ddVVdF2UgG8NOsxtuk_UrWDYuMTYLuPihBrh4DIsP3t6IdThp1IVCFu9kwtG4nGsIkQIUOMQ8Esp-nrSjc1KDHQrkQDuM1OTUXJMRn-vIvFoelOxTllcaJRfJ0v3qzMxxENBU0Hw?key=088haGOHbd6Uu7p3CTdxVA)

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeldd6-jPJiRXXchTTQ4ueu2j7PrqucKnR5L1sur4wjnkTju3N2U1NHemtag1RVkwcPWhOYLQTNMwsc_8HA8xne9hGqkVPQMgvzpRhXruLKwco6idOOuICqvKWHNnx_-SGA6KhH14q3SyDorAbh4nU7DOLe?key=088haGOHbd6Uu7p3CTdxVA)

Caso apresente a mensagem de erro, verificamos direto na raiz, acessando servidor e realizando testes como: ping, traceroute, nmap, radsniff. Com ping validamos se o host está ativo de fato, com traceroute verificamos se há algum problema no caminho entre os dispositivos, com nmap verificamos todas aportas que estão abertas, fechadas ou filtradas, e pesquisar especificando uma porta, com isso podemos validar no ixc se a porta está correta, verificar se por algum motivo de firewall aquela porta não está livre para o ip do ixc. Utilizando o radsniff podemos colher logs úteis que o ixc retorna quando clicamos na ação de desconectar.

  

Mikrotik

- Validar se de fato o cliente está conectado, pois, se não houver a interface daquele login ativa o ixc não encontrará o que você solicitou e retornará um erro.

- Validamos a porta da api, se está habilitada e condizente. 

- Checagem do avaible from (“disponível para: {ip ou faixa}” tanto para o user quanto para a porta da api), o avaible from seria para regrar que aquele usuário só poderá logar a partir de determinado IP ou faixa, analisamos se o ip que está indicando é do servidor ixc ou se cabe em um range estabelecido.

- Checagem do radius, verificar o ip address e o source address, geralmente ocorre muito do pessoal mexer e trocar. Verificar a porta se não foi alterada, e não menos importante o login e senha.

- Verificar se a opção logar bloqueio está ativa, normalmente o pessoal confunde muito essa questão, primeiro, porque o ip que fica registrado é o último que o login pegou, e em segundo, o cliente tenta desconectar aquele login e não consegue por simplesmente não ter autenticado.

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdZx82JnzFq2vmjYroR-QerHh2475eku40aCIC6o3P5XIw3MUvs35lumZMn3UDZi5pJej68o0yoROd-68DyZufqXQm8lFCuNONRN388yd1nHqlyOlST4i04ZcGYF1b6FJzoQCq5GXVyK3y0PfqT6j_3q468?key=088haGOHbd6Uu7p3CTdxVA)![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfDONJL4F0d_g61yq6p1WoLoxCDicLKkVXu8h68vwyNVNi3Fpq_ojxMu6KOqu8fvUsVHPwNx_oKpoSdbEvECrpIy0R4inLbIi9kHmiejaxiq7Od5nr_bHyiUwNBP14he8vbUJfssa8rhRD_i68itUpSh-_5?key=088haGOHbd6Uu7p3CTdxVA)

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcOIyjeyn1I46HjQRtlRUl3hqXfcCfDA9T7EvbYC5yl-8mWcArXA53SuUk3sspaO_J8GPNF6uYqO0tMqSwuqDQ3kqiCvwJuPkWg6hQD_DGX9br77BoT-EZnH6xfbeViONI4ATu5KP66fH_CYZejcFmYmw?key=088haGOHbd6Uu7p3CTdxVA)

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXev9lAzmNCc3k0XjNJxZG0krRZLIJVdmeHCqzf4Vhsx1ADS_ugwK36zLIvHJd4YBmb7SHTFIAQlX1odPyu5rGt7e27mTkQdh9fFuhUDaug2VTQ9lxwTIl_AHpHRJKXLH-zk23OdyFa9tTzVOdqBsut14cKu?key=088haGOHbd6Uu7p3CTdxVA)

  
  

Huawei 

  

- Authentication ID do router não corresponde com o ID que o Ixc coletou. Geralmente é o que mais ocorre em Huawei e que, em específico, é o problema que eu mais tratei. De início fazemos a validação verificando o botão de desconexão, após validação, verificar se o cliente está conectado:

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXe1acGvJa6i_7XmlewTLg57c2mKyeVZuciIA5BieOjCSgH4zxek2168_1kaMUe-cFotb1ZRx_T-P5ED5NIr5dLwe4rOluJM9hH5oiMoLBVwZ-p_soKPA21iTZcv2F-iCpSx9sEVMOOLpGH_0ZYQGF7ba9Nk?key=088haGOHbd6Uu7p3CTdxVA)

Se o cliente estiver conectado, irá ser retornado informações da conexão como vlan, ip, etc.

Caso retorne “no online user” significa que o usuário não está logado.

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcc4TYsGRtPyzSXUOyyTxwfHi3G50-B0FA1sHIokQ_yIIQZ5A48N2mMnwZooya34kdYdikiiYvJ6LRaEkZCZm6eiiehDk4Wq1V-223zImnEWGSNCPP6oCbvL6-S6zbfaFUMEhnTje6qy0dEYNMzAbdMhRri?key=088haGOHbd6Uu7p3CTdxVA)

Com o parâmetro verbose, conseguimos verificar mais informações sobre aquela conexão, e uma das informações será o authentication id, e é isso que verificaremos.

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXd-bXiOGSizR87SR4frcOc7lGhhk_ClSodIvJTNpoJMmrP4HDnrte1XDCCvBrwaEXaoEDNdl8ziVAVdCLSoyeqByf_wvegoeQIqftpnXjvNLlzeAkLE7cWyY_51eHWc0WcLhDUr8oj2x3eTdJR-e_DhRjVn?key=088haGOHbd6Uu7p3CTdxVA)

Dentro do ixc, acessando um login, na aba concentrador estará indicando esse ID. 

Caso ele não seja o mesmo que a gente viu lá no concentrador, o IXC não conseguirá localizar essa sessão, impossibilitando a desconexão do cliente.

- Conectar clientes com bloqueio. Como mencionei antes no caso do mikrotik, há uma certa confusão quando a opção não está ativa e o usuário tenta desconectar um login e não acontece, nesses casos, validamos a autenticação no concentrador e descobrimos um “no online user”. Mas por que ainda aparece conectado e não consigo desconectar? E o pior de tudo, o cliente está com faixa de navegação!

Exatamente por não permitir autenticação por bloqueio, o registro do último ip coletado foi de cgnat e o status de online é por ele não encontrar mais aquela sessão, daí a solução manual para resolver a exibição, é via banco, ou quando o cliente conectar novamente (sem bloqueio dessa vez, ou com a opção de logar bloqueio ativada)

  

Bônus:

  

- Firewall: É claro que o firewall incluí no diagnóstico primário que relatei no início do tema, mas queria citar um ponto importante, quando por algum motivo o concentrador nega a conexão do servidor do IXC. 
    

  Obviamente não é regra, pois dependerá muito de como está estruturada a rede do cliente, mas apresento essa solução que pode ajudar em casos que estejam em nosso alcance:  
  
Criar uma rule no firewall com aceppt para o ip do ixc, segue uma breve demonstração no mikrotik, mas isso vale para os outros também:

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdDiwMkEEEjNRyI3BNgJonenPPpDthi-u8FstschuVwX8-469vW3RqsbDyxTPu1ateBn_IHtCYb_CcHs7CGGk7h4vbmeKn4BpiQHoDiNyIttw13UP0qusR8gOyVnQwA-ICcYVRGp309rzoUiAPhR-jPQwTj?key=088haGOHbd6Uu7p3CTdxVA)![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeHU96SKLQg-JhQu3V4UwUo1z2VLAZeTbMwMGQT3Imy7byJF9NfTbIW3v1HG5Nr66SH7QkaMvTnsZgkac2Zh4vko5VeFy_eXVpb8AgjGWqTpg-NYhNg9zRKEERRMlbmszrJIZzvT9VpFa1OaBtIh776TH0?key=088haGOHbd6Uu7p3CTdxVA)

  
  

Obrigado, pela atenção!

  
  
  
  

Tenho essas dúvidas aqui enquanto elaborava esse documento:

  

- Não tenho certeza, mas me confirma se de fato é o verbose que vai me mostrar o authentication ID.
    
- Na minha cabeça, da última vez que vi o campo session ID, eu achava que tava escrito authentication ID também, me informa se olhei no local correto. Pode ser porque a base de exemplo é um pouco antiga, não sei.
    

  

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfLGl4i4q2CZ-sZZWHnPJaCF2TdyY7r_dgumXESJNdleVPykBqMmFyyoKb6KRLVm3xwoNQWXbip06oVWQkM5HB8zQOxeJmDW9OUxuhaHJmhESMZOltfCliZ2VT9MYqI__9uEZ_cGiMMdN1EAO-V0bIo5BE?key=088haGOHbd6Uu7p3CTdxVA)

**