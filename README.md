<h3 align="center">Status da apostila:</h3>
<p align="center"> 
    <img src="https://progress-bar.dev/50/"(https://progress-bar.dev/50/ width="130")>
 </p>
<br><br>

![HTTP: Entendendo a web por baixo dos panos](https://user-images.githubusercontent.com/69727594/142417931-50aea50c-2fb0-424d-8ed1-1b5d547eb1af.png)
## Apostila de HTTP

Oiê, tudo bem?
Essa apostila foi criada para te ajudar a entender mais sobre o HTTP! Espero que consiga te ajudar. 🥰

> Em caso de dúvidas ou feedbacks, não exite em falar comigo!

### Sumário:
- [🧐 O que é HTTP?](#o-que-é-http--voltar-ao-topo)
- [🖥️ A web segura - HTTPS](#a-web-segura---https--voltar-ao-topo)
- [🌍 Endereços sob seu domínio](#endereços-sob-seu-domínio--voltar-ao-topo)
- [😉 O cliente pede e o servidor responde](#o-cliente-pede-e-o-servidor-responde--voltar-ao-topo)
- 👨🏻‍💻 Depurando a requisição HTTP (**Em breve**)
- 📐 Parâmetros da requisição (**Em breve**)
- 🤓 Serviços na web com REST (**Em breve**)
- 🌱 HTTP2 - Por uma web mais eficiente (**Em breve**)
- 🤩 Final (**Em breve**)
- [🥰 Agradecimentos e créditos](#agradecimentos-e-créditos--voltar-ao-topo)
#

![O que é HTTP?](https://user-images.githubusercontent.com/69727594/142418569-fec7a598-9e5c-436b-9702-02215eed27e3.png)
## O que é HTTP? ([🔝 Voltar ao topo](#apostila-de-http))

O HTTP, ou *Hypertext Transfer Protocol*, é um protocolo (conjunto de regras) de comunicação utilizado para sistemas de informação de hipermídia, distribuídos e colaborativos. Traduzindo, é ele que possibilita que as pessoas que inserem a URL de um site consigam ver os conteúdos e dados dele e ele é o **protocolo mais importante da internet!**

👦🏻 : Qual a origem do HTTP?

O físico Tim Berners-Lee e sua equipe foram os responsáveis por inventar o HTTP original, juntamente com o HTML e a tecnologia associada para um servidor da Web e um navegador da Web baseado em texto... É uma história um tanto complicadinha de explicar em poucas palavras! 😆
> Quer saber mais? Clique [nesse link](https://rockcontent.com/br/blog/http/) e conheça a história completa do HTTP! 😉

Uma das perguntas no curso da Alura é: *O protocolo HTTP segue o modelo Client-Server. O que o navegador (como Chrome ou Firefox) representa nesse modelo? O cliente ou o servidor?*

Bem, a resposta é **Cliente**.
<br><br>
👦🏻 : Por quê?

Exemplificando, digamos que você está entrando no site da Alura para acessar um curso. Quem **está usando o navegador** (no caso, você) é **cliente** da Alura. Do outro lado, a **Alura** é quem nos **fornece o conteúdo do site**, logo, ela é o **servidor**. Então, o HTTP é um protocolo que define as regras de comunicação entre cliente e servidor na internet.

<img align="right" src="https://user-images.githubusercontent.com/69727594/142423209-4f77ad49-2f23-4351-9f70-f0bc0604d1f2.png" width="500">

O HTTP foi feito para estabelecer regras de comunicação entre o modelo **Cliente-Servidor** que funciona na Web.<br>

Assim como o idioma mais fácil para você é o português, o mais fácil para a internet é o HTTP. Ele que é o responsável por definir a forma de como os dados são transportados na rede e, por isso, todo mundo que o conhece poderá receber e enviar dados.
<br><br>
> Ficou claro para você? Se sim, role para baixo para descobrir mais sobre o HTTP!<br>
> Caso esteja com dúvidas, me manda uma mensagem no [LinkedIn](https://www.linkedin.com/in/rebecalvesousa), ou um [e-mail](mailto:becabelin@gmail.com)!

#
![A web segura - HTTPS](https://user-images.githubusercontent.com/69727594/142870414-746870d7-7ae1-467c-bd9b-e247708c6b17.png)
## A web segura - HTTPS ([🔝 Voltar ao topo](#apostila-de-http))

Sabemos que, ao usar o HTTP, *todos os dados* enviados entre o cliente e o servidor são transmitidos em **texto puro**. Isso é **perigoso**, uma vez que até seu **login e senha** podem ser vistos pelas *ferramentas do desenvolvedor do navegador* (na parte de Network).

Além disso, quando o navegador solicita dados, estes passam por vários intermediadores até chegarem no servidor que os pediu.
> Por exemplo, usando uma conexão Wi-Fi, os dados do navegador passam primeiro para o roteador Wi-Fi, e do roteador passam para o modem do provedor, do modem para algum servidor do provedor de internet.<br>
> (Fonte: Alura)

Resumindo, com o HTTP você corre riscos de ter seus dados vazados por intermediários.

Para evitar perda de dados e garantir a sua segurança, existe o **HTTPS**. Ele é como o HTTP comum (inclusive a única diferença nas palavras é o S no final), mas ele tem uma camada de segurança/criptografia a mais. Antes a camada era SSL, porém hoje ela é TLS (ainda se tratam da mesma questão de segurança).

- HTTPS: Hyper Text Transfer Protocol Secure
- SSL/TSL: Secure Sockets Layer / Transport Layer Security

<img align="left" src="https://user-images.githubusercontent.com/69727594/142886593-ddc4d685-b6b6-4ccf-8539-b9b711e84fc6.png" width="500">

Se você reparar, ao lado esquerdo de um site HTTPS, você verá um cadeado. Ele significa que o site em que você está é seguro, ou seja, você não correrá o risco de ter seus dados vazados em algum momento.

O HTTPS usa criptografia baseada em chaves públicas e privadas e para gerar essas chaves é preciso garantir a identidade de quem possui essas chaves. Para garantir essa identidade em seu site, você precisará de um **certificado digital**. Um certificado digital é utilizado para identificar determinada entidade e a para geração das chaves de criptografia.

Depois do certificado, é preciso que uma autoridade certificadora, que nada mais é que um órgão ou entidade confiável (como a [COMODO RSA Domain Validation](https://comodosslstore.com/resources/what-is-comodo-rsa-certification-authority/)), garanta não apenas a identidade do site mas também a validade desse certificado.

👦🏻 : Legal, mas como tudo isso funciona?

<img align="right" src="https://user-images.githubusercontent.com/69727594/142886484-43dced06-e352-4af3-aa38-e9d514573b06.png" width="500">

1 - Os navegadores que tem uma chave pública criptografam as informações<br>
2 - Essas informações são enviadas para o servidor<br>
3 - O servidor as descriptografa com a chave privada<br>

É importante notar que apenas a chave privada descriptografa as informações criptografadas com a pública, e também que deve-se manter a chave privada segura. Além disso, o certificado digital tem data de validade, então se ela expirar e você não renovar o certificado, seu site deixará de ser seguro!

#
![Endereços sob seu domínio](https://user-images.githubusercontent.com/69727594/142948618-e0b340a4-a42b-47d4-83a0-e915ba1a6e66.png)
## Endereços sob seu domínio ([🔝 Voltar ao topo](#apostila-de-http))

Recapitulando os capítulos anteriores, os sites serão escritos com o começo ```http://www.seusite.com.br```(não seguro) ou ```https://www.seusite.com.br```(seguro). O que você não sabe ainda (ou sabe?) é que o ```www.seusite.com.br``` não é necessariamente o *nome do seu site*, mas o nome do seu **domínio**!

<img align="left" src="https://user-images.githubusercontent.com/69727594/142949364-2fc69ad3-8123-4fb4-957f-0d907132b95f.png" width="300">

Analisando o site ```https://www.seusite.com.br```, vemos que, da direita para a esquerda, a primeira palavra é o ```br```. O ```br``` é o *top level domain*, ou seja, está na raiz do domínio. Logo depois vem o ```com```, que é a abreviação de *comercial* e o ```seusite```, os dois são **subdomínios**.

> Para saber mais:<br>
> A abreviação ```www``` representa o [***world wide web***](https://www.google.com/search?client=opera-gx&q=world+wide+web&sourceid=opera&ie=UTF-8&oe=UTF-8).<br>
> O ```www``` é opcional, já que, com ou sem ele, a mesma página aparecerá. Contudo, o uso ainda é muito popular.

Os **subdomínios** são como sessões específicas dentro de um site. Um exemplo no curso da Alura é o do Google. No Gmail temos o endereço: ```mail.google.com``` e no Google Drive: ```drive.google.com```. Tanto o Gmail como o Drive são **subdomínios** do domínio Google.

Esses subdomínios apontam para páginas diferentes dentro do mesmo domínio (Google).

Pra te mandar a real, os domínios foram organizados em uma hierarquia criada só para organizar os sites dentro da internet e a gente poder lembrar dos nomes. Ou seja, a internet funciona tranquilamente sem os domínios.

👦🏻 : Mas se as máquinas não precisam dos nomes, como elas chegam nos sites?

Bem, elas usam o que se chama de endereços de IP, que nada mais são do que números - o que é muito difícil da gente decorar.

Mas não se preocupe com números! IP's são mais importantes para quem trabalha com rede. O desenvolvedor normalmente não precisa mexer com isso.

👦🏻 : Só que a gente não entra nos sites usando o IP, então como o domínio consegue pegar esse IP e transformar numa [URL](https://www.google.com/search?client=opera-gx&q=url&sourceid=opera&ie=UTF-8&oe=UTF-8)?

Quando digitamos a URL de um site, essa URL é transformada em um número pelo [DNS (Domain Name System)](https://aws.amazon.com/pt/route53/what-is-dns/).
O DNS é um serviço transparente que age como um grande banco de dados de domínios. Então, quando você digitar a URL de um site, o DNS a transforma em um IP e você consegue acessar! Incrível, não? 🤩

> Não diz que fui eu quem te contou (até porque eu roubei essa informação da Alura 😆), mas você pode escolher um servidor DNS de preferência! Inclusive, um dos mais utilizados é o da própria [Google](https://developers.google.com/speed/public-dns/)

Sabendo de todas essas coisas, imagine que o servidor é uma casa. Se for uma mansão, ela terá várias portas; e se for uma casinha pequena, terá umas 2 ou 3, certo? Os servidores são assim também, eles podem ter várias portas e o que você precisa saber é qual porta utilizar quando chegar na casa. Ou seja, você deve saber qual porta é utilizada para os protocolos HTTP e HTTPS!

<img align="right" src="https://user-images.githubusercontent.com/69727594/142951437-95870f7c-fe45-46ef-851e-f4a071ad2d76.png" width="300">

A porta padrão reservada para o protocolo HTTP é o ```80``` e a do HTTPS é o ```443```. Se você digitar ```:80``` no final da URL de um site HTTP (como no exemplo da Alura ```http://www.alura.com.br:80```) ou ```:443``` no final de um site HTTPS, verá o próprio navegador a escondendo. Porém, se você trocar o 80 e 443, por exemplo, por 81 e 442, verá que os site não conseguirão carregar.

👦🏻 : Por que isso acontece?

Simplesmente porque a porta não está aberta. Não podemos estabelecer uma conexão e o tempo de conexão vai esgotar.

> Vários protocolos têm a sua própria porta padrão, como o FTP que usa ```21``` e o SSH que usa ```22```.

Agora, repare no site ```https://seusite.com.br:443/inicio```. Você sabe o significado de tudo até o 443, certo? Agora, sabe me dizer o que é o ```/inicio```?

Ele se chama *recurso*. Dando como exemplo o site da Alura, existem diversos recursos lá: para ver as carreiras tem o ```/careers```, já para visualizar os fóruns tem o ```/forum```, para ver a sua dashboard tem o ```/dashboard``` e por aí vai. Basicamente, os recursos são caminhos para acessar as funcionalidades/páginas do site que você está acessando.

Então, se você perceber todos os sites seguem este padrão: ```protocolo://dominio:porta/caminho/recurso```. Esse padrão é a nossa famosa URL, que eu falei lá em cima! Então, as URLs são os endereços na web! Super legal, né?

#
![](https://user-images.githubusercontent.com/69727594/142953447-bf52f888-974f-49a6-8fdf-682180d4fef0.png)
## O cliente pede e o servidor responde ([🔝 Voltar ao topo](#apostila-de-http))

Já sabemos bastante sobre o HTTP, não é mesmo? Só que ainda tem mais coisas, viu? 😅

Quando queremos fazer login em algum site, preenchemos o formulário e clicamos no botão de enviar. O navegador envia o nosso login e a nossa senha para o servidor através do protocolo HTTP, certo?

No mundo HTTP, a requisição enviada pelo navegador para o servidor é chamada de **HTTP REQUEST**.<br>
Se o nosso login for válido, somos direcionados para outra página, e essa essa resposta no mundo HTTP é chamada de **HTTP RESPONSE**.

A comunicação segue **sempre** esse modelo: o cliente **envia uma requisição** e o servidor **responde**. Ela (a comunicação) **sempre começa com o cliente**: é ele quem pede as informações. O servidor responde **apenas** o que foi requisitado e **nunca inicia a comunicação**!

Se navegarmos pelas páginas de um site, por exemplo, ao clicarmos em alguma seção enviamos uma nova requisição e percebemos que **toda** a página foi trocada. A ideia do HTTP é essa, cada recurso é **independente** do outro e **não depende do anterior**. Isso também se aplica para os dados enviados na requisição: cada requisição é independente da outra e ela sempre deve conter todas informações para o servidor responder. Essa característica de cada requisição ser independente é chamada de **stateless**.

<img align="left" src="https://user-images.githubusercontent.com/69727594/144228680-050505e0-9b20-47b8-8861-1a4be5a670f6.png" width="500">

O HTTP é um protocolo que **não mantém o estado de requisições**. Só com HTTP **não há como se lembrar das requisições anteriores** enviadas para o servidor. Por isso precisamos incluir em cada requisição todas as informações, sempre. 

👦🏻 : Mas, quando eu faço meu login na Alura, por exemplo, aparece todas as informações que eu coloquei na primeira vez que entrei. Por que isso acontece?

Cada requisição deve enviar **todas as informações para gerar a resposta**. Ou seja, o navegador envia em cada requisição informações sobre o seu usuário. Então, se cada requisição for **independente uma da outra**, e não tiver como se lembrar das **requisições anteriores**, é certo que o navegador envia os **dados sobre o meu usuário** em **cada requisição**.

👦🏻 : Então o navegador envia o login e senha em cada requisição?

A resposta é **não**. Quando efetuamos o login, a Alura valida os nossos dados, certo? Nesse momento, o servidor tem certeza que o usuário existe e gera uma **identificação** quase aleatória para o usuário. Essa identificação é um número criado ao vivo e muito difícil de adivinhar. Esse número é a **identificação temporária** do usuário e ele será devolvido na resposta.

👦🏻 : E o que são esses famosos **cookies**?

Sabe essa **identificação** que eu acabei de falar? O navegador grava esse número em um **arquivo especial** para cada site, são os famosos **cookies**.

> Se você estiver usando o navegador Chrome, pode ver os cookies do site que está logado em ```Configurações -> Privacidade -> Configurações de conteúdo... -> Todos os cookies e dados de site...```

Se você **apagar** um cookie de **login**, por exemplo, **perderá sua identificação**, e aí o site exigirá um **novo login** pois não lembrará que você já estava logado.

A ideia de manter dados entre requisições é algo muito comum no desenvolvimento de aplicações na web. Um usuário que se loga no sistema web causa a **criação de uma sessão**. Uma sessão então é útil para **guardar informações sobre o usuário e ações dele**. Um exemplo é um carrinho de compras: entre várias requisições estamos usando o **mesmo carrinho de compras** que guarda os nossos produtos escolhidos.

Resumindo, uma sessão HTTP nada mais é que um **tempo que o cliente permanece ativo no sistema**. Ou seja, quando você se desloga de um site, ele termina a sua sessão.

#
![Agradecimentos e créditos](https://user-images.githubusercontent.com/69727594/142418935-56f66bb7-5563-4e6e-9f47-84931290fd6a.png)
## Agradecimentos e créditos ([🔝 Voltar ao topo](#apostila-de-http))
Espero que você tenha gostado do conteúdo e que eu tenha conseguido te ajudar!

Agradecimentos:
- [Alura](https://www.alura.com.br) e sua equipe de professores, por todo o conhecimento ensinado!

Créditos e fontes:
- [Rock Content](https://rockcontent.com/br/blog/http/)
- Pai de todos, o famoso [Google](https://www.google.com)
- [Amazon AWS](https://aws.amazon.com/pt/route53/what-is-dns/)
