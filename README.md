<h3 align="center">Status da apostila:</h3>
<p align="center"> 
    <img src="https://progress-bar.dev/80/"(https://progress-bar.dev/80/ width="130")>
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
- [👨🏻‍💻 Depurando a requisição HTTP](#depurando-a-requisição-http--voltar-ao-topo)
- [📐 Parâmetros da requisição](#parâmetros-da-requisição--voltar-ao-topo)
- [🤓 Serviços na web com REST](#serviços-na-web-com-rest--voltar-ao-topo)
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
![Depurando a requisição HTTP](https://user-images.githubusercontent.com/69727594/144232320-ac0632f8-0db4-40e0-ae38-1cedd59fc13d.png)
## Depurando a requisição HTTP ([🔝 Voltar ao topo](#apostila-de-http))

Para mostrar mais detalhes sobre a comunicação HTTP, navegadores mais populares como Google Chrome, Mozilla Firefox ou Microsoft Edge possuem ferramentas e plugins que visualizam como o navegador trabalha e usa o HTTP.

> Para habilitar as ferramentas do desenvolvedor no Chrome vá ao menu à direita (as reticências na vertical): **Mais ferramentas -> Ferramentas do desenvolvedor, ou no menu superior: Ferramentas -> Ferramentas do desenvolvedor**. Após isso, selecionamos a aba **Network**.<br><br>
> No Firefox vá ao menu superior: **Ferramentas -> Desenvolvedor web -> Exibir/Ocultar ferramentas**.<br><br>
> Para o Internet Explorer aperte a tecla **F12** para abrir o **console do desenvolvedor** e selecione a aba **Rede (ou Network)**.

<img align="right" src="https://user-images.githubusercontent.com/69727594/144234189-70ee0b60-695d-43e1-838b-bf30477cc250.png" width="700">
Usando o site da Alura como exemplo, no console podemos ver todas as requisições HTTP executadas pelo Chrome. Não só isso, mas também aparecem alguns códigos e métodos, além do tempo de execução para cada requisição. Repare que chamamos apenas o http://www.alura.com.br, mas foram feitas várias outras requisições em seguida.

Na primeira coluna aparece a URL (o endereço) e na segunda coluna o método HTTP (indica qual é a intenção ou ação dessa requisição). Queremos receber informações, sem modificar algo no servidor, que é justamente a ideia do método GET, ou seja, enviamos uma requisição com ela.

Como resposta recebemos o código de status **301**. O protocolo HTTP define alguns códigos padrões para esclarecer a resposta. Indo com o mouse em cima do 301 o Chrome mostra o significado desse código: **Moved Permanently**. Ou seja, o site Alura foi movido para outro lugar.

👦🏻 : Ué, então para onde ele foi?

<img align="left" src="**https://user-images.githubusercontent.com/69727594/144234714-512d3ac7-23e9-4b32-8710-519788b0934b.png**" width="600">

A localização ou a URL concreta está na **resposta HTTP**. Ao clicar em cima do código de status 301 para receber mais informações, o Chrome mostra todos os cabeçalhos da requisição e da resposta. Dentro do item **Response Headers** podemos ver todos os cabeçalhos que o servidor devolveu e logo apareceu um com o nome **Location**. Esse cabeçalho indica a nova URL, só que agora usando **https**.

Resumindo, quando o navegador recebe o status **301** ele já sabe que é preciso enviar uma **nova requisição** e procura a **nova URL** no cabeçalho de resposta **Location**.

Se alguém acessa a Alura usando http (inseguro) automaticamente é chamado o site seguro (https). Isto é um comportamento muito comum para garantir que usamos https sempre. Se esquecermos de usar https, o servidor devolve o status 301 com a nova localização, mas agora usando https.
Ao receber o código **301**, o navegador chama automaticamente a nova URL. No mundo de desenvolvimento web este comportamento é chamado de **Redirecionamento pelo navegador**, ou **Redirecionamento no lado do cliente**, pois fomos redirecionados para o recurso correto.

O código **200** é um dos códigos mais comuns e significa que tudo deu certo! Dessa vez não foi preciso fazer um redirecionamento (não tem o cabeçalho Location na resposta) e não deu nenhum outro problema.

<img align="right" src="https://user-images.githubusercontent.com/69727594/144236055-91371167-d8ec-4369-8efa-4b14a0eded78.png" width="300">

No console também podemos ver que aparecem mais requisições (cada linha representa um novo request). Quando o servidor devolve a resposta para o navegador vem o conteúdo da página inicial em um formato especial, chamado de **HTML**. É ele que define a estrutura da nossa página, ou seja, os menus, botões, links, etc. Mas, lembre-se, dentro do HTML não vêm as imagens e outros arquivos necessários para deixar o site perfeito. Dentro dele vem apenas a URL (endereço) desses outros recursos.

Então, ao receber o HTML, o navegador dispara várias outras requisições para carregar as imagens, fontes e outros dados. Como também são requisições HTTP, o console mostra suas informações. Podemos ver que na resposta vem o tipo do conteúdo, por exemplo text/html, text/css, image/svg+xml, entre outros.

Enfim, o protocolo HTTP não está preso em algum formato específico, podemos trafegar qualquer informação com ele.

<img align="left" src="https://user-images.githubusercontent.com/69727594/144236688-2b6e736c-bc05-43a6-8343-bd307e03f259.png" width="700">

Se tentarmos entrar em uma página que não existe, dará erro. Se abrirmos o console, o código agora é **404**. No mundo HTTP, **404** significa que **o servidor não encontrou o recurso (Not Found)**.

Pode acontecer de, durante o desenvolvimento de uma aplicação web, ocorrerem problemas no lado do servidor. Isto é normal, pois alguma lógica pode falhar e erros acontecem no desenvolvimento (e é sobre isso, amigo). Quando algum problema no servidor acontecer, também, podemos avisar o cliente através do protocolo HTTP. O código mais comum para este tipo de problema é o **500** que significa: "deu pau no servidor".

Enfim, existem muitos códigos de resposta definidos no protocolo HTTP.

> Há tabelas disponíveis na web que mostram esses códigos, descrevendo o significado de cada um deles. No entanto, no dia a dia, o desenvolvedor não precisa decorar todos esses códigos, mas, caso queira consultar quando for necessário, você pode entrar neste site [aqui](https://www.w3schools.com/tags/ref_httpmessages.asp).

O importante é saber que:
- Começa com 2xx: **coisa boa**
- Começa com 3xx: normalmente significa que o navegador precisa **fazer algo a mais** pois algo mudou ou um recurso não existe mais
- Começa com 4xx: o navegador enviou **dados errados**, como por exemplo uma URL errada
- Começa com 5xx: caso o servidor gere algum problema

No dia a dia os códigos **200**, **404** e **500** são de longe os **mais utilizados**!

> Dica do dia:
> Veja os códigos http como [cachorros](https://httpstatusdogs.com) ou [gatinhos](https://http.cat)!

#
![Parâmetros da requisição](https://user-images.githubusercontent.com/69727594/144240266-2e6e209e-dcb1-4747-98d8-e9f85341380b.png)
## Parâmetros da requisição ([🔝 Voltar ao topo](#apostila-de-http))

Digamos que você entre no YouTube e pesquise por vídeos de Hora de Aventura (🎶 a aventura vai começar 🎶). Note que, ao pesquisar no YouTube, a URL mudou um pouco. O recurso acessado pela busca se chama /results (os resultados da pesquisa) mas agora temos um parâmetro da requisição, indicado pela ?: https://www.youtube.com/results?search_query=Hora+de+Aventura

O parâmetro se chama ```search_query``` com o valor ```Ayrton+Senna```. Esses parâmetros da URL normalmente são chamados de **Query Params**. O HTTP permite enviar mais de um parâmetro, basta concatenar o próximo parâmetro através do caractere **&**.

Por exemplo, a busca avançada do Google usa vários parâmetros para refinar a pesquisa como o idioma, o país ou data. Veja como o Google concatena os Query Params: https://www.google.com.br/?gws_rd=ssl#lr=lang_pt&tbs=lr:lang_1pt&q=neymar

No console sempre aparece o tipo (ou método) da requisição, sendo **GET**. O GET é útil quando queremos deixar os parâmetros visíveis, pois assim podemos facilmente guardar a URL com os parâmetros para repetir a requisição algum momento depois. Mas será que isso também é uma boa opção na hora de enviar credenciais como login e senha? Queremos que apareça a senha de um usuário na URL?

Imagina que você efetue o login no seu banco e na URL apareça: https://www.bb.com.br/login?login=euzinho&password=supersecreto
Isso não é nada legal, né? Acabou com todo o segredo! 😫

<img align="right" src="https://user-images.githubusercontent.com/69727594/144245966-372edb19-4e9b-44b5-85bf-46df2adf189f.png" width="600">

Vamos efetuar um login na Alura para ver como esse sistema **envia dados do usuário para o servidor**. Repare que a URL para enviar o **login e senha** se chama https://www.alura.com.br/signin. Repare também que o método HTTP utilizado mudou. Estamos usando o **HTTP POST**. Com o POST, o navegador envia os dados do formulário no corpo da requisição e não na URL (se fosse um GET, todos os dados seriam enviados através da URL) Como a Alura não deseja que os dados do login e senha apareçam na URL do navegador, foi utilizado um **HTTP POST**.

Um outro exemplo de um método POST na Alura é quando criamos uma pergunta no forum (usuário submete um formulário com dados). O método POST foi inicialmente pensado para criar algo novo no servidor como acabamos de fazer. No entanto, nem sempre isso é utilizado dessa maneira. Por exemplo, acabamos de usar um POST para verificar o login, ou seja, não alteramos ou adicionamos nada na Alura, apenas o usamos para esconder os parâmetros (seu login e senha).

Como o servidor realmente reage quando recebe uma requisição POST depende da implementação, depende da lógica atrás. Os métodos como GET e POST definem uma intenção mas o que realmente será executado depende do servidor.

Resumindo, no dia a dia, usamos GET para fazer pesquisas mas também para alterar ou remover algo no servidor. Com o POST, o usamos para inserir e alterar dados, como também para pesquisar.

Quando enviamos parâmetros na URL, devemos iniciar pelo ?, o nome do parâmetro e um =, para separar o nome do parâmetro do seu valor:
```?nome_do_parametro=seu_valor```
<br>
Quando usamos mais do que, um parâmetro devemos usar & para separá-los:
```?nome_do_parametro=seu_valor&nome_do_outro_param=valor```

Saiba que existem outros métodos HTTP como o ```DELETE``` e ```PUT```. O ```DELETE``` existe para enviar uma requisição com a intenção de **remover um recurso**, ```PUT``` para **atualizar**. No entanto, esses métodos são **poucos utilizados no desenvolvimento de aplicações web**, eles são mais importantes quando se tratam de **serviços web**.

Em geral, há **mais recursos** que o protocolo HTTP oferece, como **vários outros cabeçalhos** que especificam mais a requisição e resposta. Nessa apostila vimos os mais importantes métodos, códigos e cabeçalhos do protocolo HTTP.

#
![Serviços na web com REST](https://user-images.githubusercontent.com/69727594/144248302-62b2b3fb-8e05-4793-beec-5ed0a6de5eb6.png)
## Serviços na web com REST ([🔝 Voltar ao topo](#apostila-de-http))
Será que toda a requisição HTTP sempre tem como origem um navegador? E toda resposta só possui conteúdo que ele entende: HTML, CSS, Javascript e imagens?

Bom, neste capítulo você terá as respostas para as suas perguntas!

<img align="right" src="https://user-images.githubusercontent.com/69727594/144248936-7b375551-9447-4c1d-b26c-9f7f0fefe118.png" width="200">

Hoje existem milhões de softwares rodando ou sendo desenvolvidos em várias linguagens de programação e frameworks. Tais softwares não vivem necessariamente isolados e podem querer se comunicar de alguma forma.

Um exemplo clássico é o login via rede social/google que estamos cada vez mais habituados. Sabe quando queremos entrar, por exemplo, no Instagram e você pode se conectar pelo Facebook? Então, é exatamente isso! Essa conversa acaba sendo transparente para nós, usuários, já que exige uma autorização de acesso às nossas informações.

As aplicações que disponibilizam serviços para outras são chamadas de **webservices**. Temos serviços web para trabalhar com pagamentos (como o Paypal), upload de imagens, transformação de CEP em endereços textuais e diversos outros. Tudo isso é feito através do poderoso protocolo HTTP.

Você muito provavelmente já teve uma péssima experiência quando estava sem conexão com a internet usando um aplicativo móvel. Alguns apps não funcionam sem um acesso a rede porque as principais funcionalidades são feitas via requisições HTTP.

Essas requisições são implementadas programaticamente pelo desenvolvedor. Podemos implementá-las em várias linguagens de programação: Java, PHP, Javascript etc.

Usando o exemplo do curso da Alura, a *AluraFood* tem duas equipes em ação: a do **serviço web (ou simplesmente API web)** e a dos **apps mobile(Android e iOS)**.
Os desenvolvedores responsáveis pela tela de listagem de restaurantes vão precisar **receber do serviço** os **detalhes de cada restaurante**. Felizmente o pessoal responsável pelo webservice já documentou exatamente o que seria necessário:

```Listagem de todos os restaurantes --> GET - http://alurafood.com/api/restaurante```

<img align="center" src="https://user-images.githubusercontent.com/69727594/144250346-9040fd13-4db8-448e-96b1-28cdbc9412ed.png" width="550">

Perceba que, como resposta desse código, temos uma listagem de restaurante sendo apresentada dentro de uma tabela (elemento table do HTML) e cada linha (elemento tr) possui 4 colunas (td). Dentro de cada coluna temos as informações dos restaurantes: nome, nota de avaliação, endereço e logo.

Os responsáveis precisarão realizar uma análise do conteúdo HTML e extrair dele somente as informações necessárias. Esse ato de analisar o documento é chamado de realizar um **parsing** do arquivo. Veja que o HTML tem muito mais do que o necessário para essa equipe. Para piorar, estamos trafegando muito mais informações do que o necessário e onerando até mesmo a banda do nosso usuário. Muito chato, não? 😑

Pensando nessa deficiência do HTML, temos outros formatos que fazem mais sentido quando uma representação de um recurso (um restaurante) se faz necessário. Temos como exemplo mais legível o **XML (eXtensible Markup Language)** que poderia ser devolvido como resposta e ter o seguinte conteúdo:

<img align="center" src="https://user-images.githubusercontent.com/69727594/144251091-0ac0f503-26fd-4992-bca0-56e0ba448dff.png" width="550">

Outro famoso formato e onerando menos ainda a rede, por ser mais leve, é o **JSON (JavaScript Object Notation)**:

<img align="center" src="https://user-images.githubusercontent.com/69727594/144251274-1305387a-7c59-423a-aa99-585755e88283.png" width="550">

Mas como especificar à aplicação de serviço que gostaríamos de receber em um formato JSON? Via **cabeçalho HTTP**!

Para indicar que queremos resposta no formato JSON usa-se um **Accept: application/json** como cabeçalho HTTP. Por outro lado, já na resposta uma indicação desse conteúdo é especificado pelo cabeçalho **Content-Type: application/json**.

Tudo certo para a listagem de restaurantes. Mas será que o app AluraFood se resume a listar restaurantes? Provavelmente não, dado que o usuário efetua pedidos, um restaurante tem cardápio que poderia sofrer alterações e por aí vai.

Algumas funcionalidades específicas aos responsáveis de um restaurante podem ser necessárias. E para isso o webservice deveria estar preparado também para lidar com essa necessidade:
```Listagem de todos os restaurantes --> GET - /restaurante```<br>
```Adicionar um  restaurante --> POST - /restaurante```

Perceba que no exemplo fictício as duas primeiras URIs são idênticas e a funcionalidade muda completamente a partir do método HTTP usado:<br>
GET -> Listagem<br>
POST -> Criação<br>

Logo podemos perceber que o **padrão** usado pela equipe do webservice define que uma **requisição web** tem **três tipos de componentes importantes**: recursos (URI), operações (GET, POST, PUT, DELETE/...) e representação de dados(XML, JSON, ...).

Esses três componentes em conjuntos seguindo algumas práticas são a base para o modelo arquitetural **REST (Representational State Transfer)** ou em português **Transferência de Estado Representacional**.

<img align="right" src="https://user-images.githubusercontent.com/69727594/144252917-c6ceb777-8374-414d-a5e5-01581ebf6e3d.png" width="400">

Ao criar as URIs do nosso sistema devemos levar em conta que elas representam recursos, não ações. Em sistemas REST, nossas URIs devem conter **apenas substantivos**, que são nossos recursos: ```/restaurante/adiciona``` **não é uma boa URI**, pois **contém um verbo** e **não está identificando um recurso**, mas sim uma **operação**.

> Para representar a adição de um restaurante podemos usar a URI /restaurante com o método HTTP POST, que representa que estamos adicionando alguma informação no sistema.

O protocolo HTTP possui operações através de métodos como: ```GET```, ```POST```, ```PUT``` e ```DELETE```.
Cada método tem uma semântica diferente e juntando o método à URI deveríamos conseguir representar todas as ações do nosso sistema.

As semânticas principais são:
- ```GET``` - **recupera informações** sobre o **recurso identificado pela URI**. Uma requisição GET **não deve modificar nenhum recurso do seu sistema**, ou seja, não deve ter nenhum **efeito colateral**, você **apenas recupera informações do sistema**.
- ```POST``` - **adiciona informações** usando o recurso da URI passada. Pode **adicionar informações a um recurso** ou **criar um novo recurso**.
- ```PUT``` - **adiciona (ou modifica)** um recurso na URI passada.
- ```DELETE``` - **remove o recurso** representado pela URI passada.

Quando fazemos uma aplicação não trafegamos um recurso pela rede, apenas uma representação dele. E essa representação pode ser feita de diferentes formas como JSON, XML ou HTML. Finalizando, nossas URIs devem **representar recursos**, as operações no recurso devem ser indicadas pelos **métodos HTTP** e podemos falar **qual é o formato em que conversamos com o servidor** com o **Content-Type** e **Accept** que são **cabeçalhos do HTTP**.

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
- [W3 Schools](https://www.w3schools.com/tags/ref_httpmessages.asp)
