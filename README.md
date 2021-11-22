<h3 align="center">Status da apostila:</h3>
<p align="center"> 
    <img src="https://progress-bar.dev/30/"(https://progress-bar.dev/30/ width="130")>
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
- 🌍 Endereços sob seu domínio (**Em breve**)
- 😉 O cliente pede e o servidor responde (**Em breve**)
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
![Agradecimentos e créditos](https://user-images.githubusercontent.com/69727594/142418935-56f66bb7-5563-4e6e-9f47-84931290fd6a.png)
## Agradecimentos e créditos ([🔝 Voltar ao topo](#apostila-de-http))
Espero que você tenha gostado do conteúdo e que eu tenha conseguido te ajudar!

Agradecimentos:
- [Alura](https://www.alura.com.br) e sua equipe de professores, por todo o conhecimento ensinado!

Créditos e fontes:
- [Rock Content](https://rockcontent.com/br/blog/http/)
