# BOOTSTRAP

*Bootstrap passo a passo: Guia para completo*

## O que é o Bootstrap?

É o framework front-end, atraente e muito intuitivo, para o desenvolvimento web mais rápido e eficaz.

O Bootstrap foi desenvolvido pelo Mark e Jacob no Twitter.

## Vantagens do Bootstrap

Ele é Mobile first, alem disso tem suporte para todos os navegadores populares.

O pacote Bootstrap inclui:

- **Scaffolding** – O Bootstrap fornece uma estrutura básica com Sistema de Grid, estilos de link e plano de fundo. Falamos sobre isso com mais detalhes na seção de Estrutura Básica do Bootstrap
- **CSS** – Bootstrap vem com o recurso de configurações CSS globais, elementos HTML fundamentais estilizados e aprimorados com classes extensíveis e um sistema de grid avançado. Falamos disso com mais detalhes na seção Bootstrap com CSS.
- **Componentes** – O Bootstrap contém mais de uma dúzia de componentes reutilizáveis criados para fornecer iconografia, menus suspensos, navegação, alertas, pop-overs e muito mais. Isso é abordado em detalhes na seção Componentes de layout.
- **Plugins JavaScript** – Bootstrap contém mais de uma dúzia de plugins jQuery personalizados. Você pode de forma fácil incluir todos eles, ou um por um. Isto é coberto em detalhes na seção de Plugins do Bootstrap.
- **Personalização** – Você pode personalizar os componentes do Bootstrap, as variáveis LESS e os plugins do jQuery para obter sua própria versão. 

---

## CONFIGURAÇÃO DO AMBIENTE BOOTSTRAP - CDN

A instalação do bootstrap é bem simples, vamos aprender a configurar a versão online do bootstrap:

````html
<head>
    <!–- meta tags obrigatórias -–>
    <meta charset="utf-8">
    <meta name="viewport" content=”width=device-width, initial-scale=1, shrink-to-fit=no">

    <title>Hello World</title>

    <!–- CSS do Bootstrap -–>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.css">
</head>
<body>

    <div class="container text-center">

    <h1 class="display-3 m-5">Hello, Bootstrap!</h1>

    <p class=”lead”>
    Use este documento como um template para iniciar qualquer projeto novo.
    Tudo o que tem aqui é esse texto e um HTML inicial, bem básico.
    </p>
    </div>

    <!–- Primeiro o jQuery, depois o Popper.js, e depois o Bootstrap JS -–>
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.js"></script>
</body>
````

Com esse template da forma como está configurado, você já é capaz de utilizar o bootstrap de forma completa. No VS Code basta digitar "b4 + tab" e todo esse template vai ser inserido na pagina, basta inserir o conteudo desse template.

Agora vamos abrir esse pagina em um navegador, para ver o resultado:

Na página Hello World que desenvolvemos, colocamos algumas classes nas tags HTML. Não escrevemos código CSS, mas percebemos que o visual da página já está com alguns estilos.

---

## CONFIGURAÇÃO DO AMBIENTE BOOTSTRAP - NPM

Agora vamos **baixar** o Bootstrap 4 e usar essa instalação em um projeto, para isso devemos ter já instalado em nossas maquinas o **Node.js** e o **NPM**, um terminal de comando como (bash, git bash, powershell, etc) e um bom editor de código (VS Code).

Para instalar o pacote do NPM no projeto (O comando npm cria um arquivo chamado package.json, com as informações necessarias sobre o nosso projeto)

- npm init -y

Para abrir o projeto direto no VS Code: $ **code .**

Vamos usar o NPM para pegar essas libs:

**Jquery: $ npm install jquery –save**


**Popper: $ npm install popper.js –save**

**Agora, vamos baixar o Bootstrap 4, também com o NPM: $ npm install bootstrap –save**

Tudo que estamos baixando vai ficar em uma pasta chamada **node_modules**, que é do NPM. É essa pasta que será o endereço das libs.

Vamos aproveitar a marcação do Hello World, e mudar só as referências do Bootstrap, do jQuery e do Popper.js.

Só que nesse caso vamos utilizar os arquivos locais (que baixamos pelo NPM), ao invés de utilizarmos os links das CDN’s:

````html
<!DOCTYPE html>
<html lang="pt-br">

    <head>
        <meta charset="utf-8">
        <meta name="viewport"content="width=device-width, initial-scale=1, shrink-to-fit=no">
        <title>Template Bootstrap</title>

        <!– CSS do Bootstrap –>
        <link rel="stylesheet" href="./node_modules/bootstrap/dist/css/bootstrap.min.css">
    </head>

    <body>
        <h1>Template Bootstrap</h1>

        <div class="container text-center”>

            <h1 class="display-3 m-5">Hello, Bootstrap!</h1>

            <p class="lead">
                Use este documento como um template para iniciar qualquer projeto novo.
                Tudo o que tem aqui é esse texto e um HTML inicial, bem básico.
            </p>
        </div>

        <!– Primeiro o jQuery, depois o Popper.js, e depois o Bootstrap JS –>
        <script src="./node_modules/jquery/dist/jquery.min.js"></script>
        <script src="./node_modules/popper.js/dist/popper.min.js"></script>
        <script src="./node_modules/bootstrap/dist/js/bootstrap.js"></script>
    </body>

</html>
````

Agora, essa página irá servir como template inicial para as outras páginas.

Assim, não vamos precisar reescrever o HTML básico e os links dos arquivos, quando formos criar uma página nova.

Se desejar, pode mudar os endereços das libs, caso queira colocar em outra pasta.

O importante aqui é que elas sejam carregadas na mesma ordem que estão, e que o endereço esteja correto.


## ENTENDENDO OS LINKS E SCRIPTS

Referencia do arquivo CSS do nosso bootstrap

````HTML
    <!DOCTYPE html>
    <html lang="pt-br">
        <link rel="stylesheet" href="./node_modules/bootstrap/dist/css/bootstrap.css">
    </html>

    Sem esse link ou se o caminho estiver errado o bootstrap não vai funcionar.

    Referencia ao Jquery, Popper.js e aos plugins do bootstrap

    <!DOCTYPE html>
    <html lang="pt-br">
        <script src="./node_modules/jquery/dist/jquery.min.js"></script>
        <script src="./node_modules/popper.js/dist/popper.min.js"></script>
        <script src="./node_modules/bootstrap/dist/js/bootstrap.js"></script>
    </html>
````

- O **jQuery** semper deve vir antes dos outros JS. O **Bootstrap** depende dele e do **Popper.js** para funcionar.

- O **Popper.js** é uma biblioteca JavaScript que tem a função de posicionar elementos como menus, tooltips e popovers.

- Por fim, observe que eu coloquei as bibliotecas Javascript por último no HTML – **isso é uma boa prática para que a página carregue mais rápido**.

- Na pasta CSS, estão todos os arquivos de estilo visuais do bootstrap e dos componentes. Para usar tudo que o bootstrap tem, é só você importar o arquivo **bootstrap.css**, ou o **bootstrap.min.css**

- Na pasta JS, ficam os arquivos com as funções dos componentes do bootstrap, como os Menus, por exemplo. Para usar todos os componentes que o bootstrap tem, é só importar o arquivo **bootstrap.js** ou **bootstrap.min.js**

- Por fim cada pasta possui uma versão padrão **(os arquivos .css e .js)** e uma versão **"minificada" (os arquivos .min.css e .min.js)** de cada script.

- Devemos usar a versão **"minificada" (ou minified)** quando for colocar seu projeto online, ou seja, em produção. Os arquivos minified como o proprio nome sugere, é bem menor que o padrão, e econimiza bastante na utilização de banda.

- Agora eu tenho um framework muito poderoso em mãos, daqui para frente, você pode começar a trabalhar com os outros componentes disponíveis do Bootstrap. 
