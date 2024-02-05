##### 01/02/2024

Curso de Vue3: explorando o framework

```
brew install node
npm install -g @vue/cli
npm run serve
npm install bulma
npm i fontawesome-free

```

@01-Iniciando o Alura Tracker 

@@01
Apresentação

[00:00] Olá. Meu nome é Vinicios Neves e eu vou te acompanhar nesse curso sobre Vue.js com TypeScript.
[00:05] Durante o decorrer do curso nós vamos desenvolver o Alura Tracker, uma aplicação que ficará responsável por fazer o tracking, o acompanhamento de tarefas diárias que executamos no dia a dia, como, por exemplo, estudar Vue.JS

[00:23] Conseguimos iniciar uma tarefa, o cronômetro vai começar a correr e quando finalizarmos ele vai começar a preencher uma lista.

[00:32] Inclusive, podemos fazer várias tarefas e ele vai incrementando essa lista de tarefas executadas, cada uma com o tempo indicado.

[00:44] Vamos utilizar nesse curso o próprio Vue na versão 3, que é um framework progressivo que vai nos ajudar em muitos aspectos, para facilitar o nosso dia a dia enquanto desenvolvedores.

[00:56] E também vamos usar o TypeScript. Então vamos juntar o poder desses dois camaradas e conseguir inferir tipo, trabalhar de uma forma diferente com o componente Vue do que fazíamos na versão 2.

[01:09] Vamos desenvolver essa aplicação. E no final ela estará publicada para você poder postar nos fóruns e compartilhar com todo mundo o que você desenvolveu.

@@02
Preparando o ambiente

Vamos precisar do NodeJS durante todo o curso. Caso você ainda não tenha o node disponível, você pode instalá-lo seguindo o passo a passo de acordo com o seu sistema operacional:
Instalação Node.js no Linux (Ubuntu)
No Ubuntu, através do terminal (permissão de administrador necessária), execute o comando abaixo:

sudo apt-get install -y nodejs
COPIAR CÓDIGO
ATENÇÃO: Em algumas distribuições Linux, pode haver um conflito de nomes quando o Node é instalado pelo apt-get. Neste caso específico, em vez de binário ser node, ele será nodejs. Isso gera problemas e a instrução npm start não funcionará, pois ela procura o binário node e não nodejs. Para resolver no Ubuntu:

sudo ln -s /usr/bin/nodejs /usr/bin/node
COPIAR CÓDIGO
Depois, o comando npm start funcionará conforme esperado.

É uma pena haver essa discrepância, mas fica aqui essa dica!

Instalação Node.js no Windows
Baixe o instalador clicando no grande botão “Windows Installer”, diretamente da página do Node.js. Durante a instalação, você apenas clicará nos botões para continuar o assistente. Não troque a pasta padrão do Node.js durante a instalação, a não ser que você saiba exatamente o que está fazendo.

Instalação Node.js no MAC
O homebrew é a maneira mais recomendada para instalar o Node.js em sua máquina, através do comando:

brew update
brew install node
COPIAR CÓDIGO
Não usa homebrew? Sem problema, baixe o instalador clicando no grande botão “macOS Installer”, diretamente da página do Node.js.

Caso tenha dificuldade na instalação do node, confira esse alura+.

Por último, baixe aqui a logo do Alura Tracker. Nós vamos utilizá-la durante o curso.

https://nodejs.org/en/download/

https://brew.sh/pt-br/

https://nodejs.org/en/download/

https://www.alura.com.br/artigos/instalando-nodejs-no-windows-e-linux?_gl=1*gyngje*_ga*MTgwMzIzMjk2Ni4xNjg4ODE5OTcz*_ga_1EPWSW3PCS*MTcwNjgyMDE5OS4xODEuMS4xNzA2ODIyMzkwLjAuMC4w*_fplc*ZFlLaklUOVhFTmRKZ0ptVmZBU3VnR25zMFBFMzg3bHRvSWlYMCUyQkVpdE04RTVJQk1LdmZ3NGU5VFZYU2plSUVQejhqVU53NkhmOHAlMkJFOGVHVUM1TUdxTEowenlINTVWM0NTUnBZTkNSYVJDeHUwcWZxa2V3RnZaSmJUZjVNdyUzRCUzRA..

https://raw.githubusercontent.com/alura-cursos/alura-tracker/main/src/assets/logo.png

@@03
Iniciando o projeto

[00:00] Durante o curso nós vamos desenvolver o Alura Tracker, essa aplicação que vai calcular o tempo gasto em cada tarefa. Então ele vai fazer o tracking, vai calcular o tempo que levamos em cada tarefa executada.
[00:17] Começar um projeto Vue requer uma série de configurações. E já pensando nisso, o Vue nos disponibiliza o CLI.

[00:31] Para instalarmos esse CLI, essa forma de criar novos projetos, precisamos já estar com o Node instalado, que está disponível no passo a passo do preparando o ambiente. E uma vez com o Node instalado podemos pedir para o NPM deixar disponível para nós.

[00:51] O -g significa de forma global, ou seja, depois que instalamos podemos solicitar comandos diretamente a partir do terminal chamando direto o comando Vue.

[01:05] Então vamos começar. Vou copiar esse comando npm install -g @vue/cli, entrar no meu terminal e pedir para ele instalar para mim o CLI.

[01:17] A única diferença é que eu preciso ter uma permissão especial, sudo no meu caso específico, porque estou usando o terminal do Mac. Então preciso do sudo npm install -g @vue/cli e ele vai instalar para mim o CLI. Esse processo demora um pouco. Quando terminar, já poderemos começar o nosso projeto.

[01:40] Com o nosso CLI instalado, já podemos criar o nosso projeto. Para isso chamamos vue create alura-tracker e conforme pedimos para o Vue criar o projeto novo, vamos selecionar manualmente o que queremos utilizar.

[02:03] Vamos marcar o TypeScript. Basta você navegar com as setas e apertar a tecla de espaço. Vou dar um “Enter” para ir para o próximo. Nós vamos utilizar a versão 3.x e não vamos utilizar componentes baseados em classe.

[02:21] Nós vamos utilizar o Babel para fazer a transpilação de código para nós. E a parte de Lint vamos deixar só com prevenção de erros e Lint on save com arquivos dedicados e não vamos salvar tudo isso para projetos futuros.

[02:42] Vamos recapitular: nós selecionamos manualmente, adicionamos o TypeScript, selecionamos a versão 3, não vamos utilizar componentes baseados em classe, vamos utilizar o Babel junto com o TypeScript.

[02:57] A parte de Linter e formatação deixamos de forma básica, fazendo o Lint na hora de salvar o arquivo e salvando todas essas configurações em arquivos dedicados.

[03:07] E por último, não vamos definir essas configurações para projetos futuros. Vou pressionar “Enter”. Ele vai seguir fazendo a instalação.

[03:18] Mais uma vez, como ele vai baixar todas as dependências e tudo que precisamos, pode demorar mais um pouco também. Assim que ele terminar, teremos o projeto pronto para começarmos a programar os nossos componentes.

[03:33] Ele já instalou, baixou todas as dependências. Agora já podemos entrar na pasta, que no caso eu chamei de “alura-tracker”. E ele já diz qual comando é necessário para fazer essa aplicação rodar: npm run serve.

[03:52] Ele vai executar um servidor para utilizarmos em tempo de desenvolvimento. Quando ele terminar de subir já conseguiremos ver um projeto iniciado.

[04:06] Vou abrir o URL. E já temos uma página de boas vindas dizendo que estamos utilizando o Vue.js com o TypeScript. Eu vou no meu Visual Studio Code e pedir para ele abrir para mim a pasta “alura-tracker”. E repare que a nossa estrutura do projeto já está toda disponível para utilizarmos.

[04:48] Ele já nos disponibiliza com o TypeScript, está importando aquele componente HelloWorld, que traz todas aquelas informações para nós.

[04:58] E se dermos uma olhada no “package.json” ele já vai nos trazer todas as dependências que nós temos para começar a programar.

[05:08] Então temos a dependência do Core e do próprio Vue, e algumas dependências em tempo de desenvolvimento, a maioria delas relacionada a TypeScript, Lint e tudo que precisamos só enquanto estamos desenvolvendo.

[05:24] Agora que já temos o CLI instalado e já iniciamos o projeto, estamos prontos para começar a escrever os nossos componentes. Como já dizia o mestre "bem começado, metade feita". Vamos começar a escrever alguns componentes em Vue.

@@04
Para saber mais: Vue CLI

Durante a criação do projeto, nós utilizamos o CLI do Vue, uma ferramenta poderosa.
Além da linha de comando, ela também possui uma interface gráfica que pode ser utilizada para a criação de novos projetos, veja:

Tela inicial do framework Vue.js

Não deixe de conferir a documentação para ficar por dentro de tudo o que pode ser feito com o CLI.

@@05
CSS externo e componentes

[00:00] Vamos agora adicionar as dependências que vamos utilizar durante o desenvolvimento da aplicação, que são duas.
[00:08] A primeira é o framework Bulma. Ele vai nos disponibilizar vários componentes, layout em colunas, que é o que vamos utilizar para dividir a nossa página.

[00:19] Então para adicionar o Bulma podemos entrar no site bulma.io, em “Documentação > Overview > Start” e temos um link para importar. Vou copiar esse link e colar dentro do nosso “index.html”, logo abaixo do title. E temos o Bulma CSS disponível para nós.

[00:46] Não é o foco do curso, você pode dar uma olhada na documentação para entender como funcionam os componentes que vamos utilizar. Mas como não é o foco eu não falarei dele, mas posso citar uma classe ou outra quando estivermos programando.

[01:00] A segunda dependência é o Font Awesome, que tem vários ícones legais para utilizar. Precisamos de um de play e stop e um ícone que representa um relógio. E precisamos instalar este pacote @fortawesome/fontawesome-free. Então no terminal vamos fazer npm i --save-dev @fortawesome/fontawesome-free e com isso ele vai ficar disponível para nós.

[01:30] Enquanto ele instala eu vou pegar o import do CSS. Vou dar um “Ctrl + C” e vamos no “main.ts” fazer um import do CSS do Font Awesome: import ‘@fortawesome/fontawesome-free/css/all.css’. E agora teremos todos os ícones disponíveis para nós.

[01:59] E agora já podemos finalmente partir para o nosso App e começar a dividir os nossos componentes. Eu vou tirar o import e o CSS base. Agora está tudo limpo. Vamos começar a dividir a nossa aplicação. Vamos envolver todo o nosso HTML numa tag main, que representa o conteúdo principal da aplicação.

[02:28] Queremos que essa tag main encapsule e faça o layout de colunas de toda a nossa aplicação. Então vou pegar as classes do Bulma que vamos precisar class “columns is-gapless is-multiline”.

[02:51] O columns indica que dentro teremos várias colunas e o is-gapless indica que o espaçamento entre essas colunas não existe. E por fim, o is-multiline indica que ele pode permitir múltiplas linhas.

[03:02] Então agora basta dividirmos em duas porções. A primeira porção é onde terá a nossa barra lateral. Vamos adicionar duas classes: eu quero que ela seja uma coluna e que o tamanho seja de um quarto do tamanho disponível.

[03:24] E tenho outra div que vai representar toda a parte da direita que tem um formulário no topo, e as listas de tarefas embaixo. Só que esse segundo quadrante terá três quartos de tamanho.

[03:45] E agora queremos criar um componente nosso. Na pasta de componentes podemos deletar o HelloWorld, porque não vamos mais usá-lo e criar um novo arquivo chamado “BarraLateral.vue”.

[04:09] O nosso componente Vue sempre será dividido em até três porções. A primeira parte é o HTML, que é o template. A segunda parte é o JavaScript, lembrando que no nosso caso estamos usando o TypeScript, então colocamos lang=”ts”. E por último, temos uma tag chamada style, em que vai todo o estilo do componente.

[04:49] Então na nossa barra lateral precisamos dividir e começar a criar pelo header. Ele é o título da aplicação.

[05:05] O H1 vai ser o título principal da página. Só que teremos uma peculiaridade: o nosso H1 será uma imagem. E precisamos substituir essa imagem. Precisamos tirar o logo do Vue e fazer o download do nosso Alura Tracker.

[05:20] Eu já fiz o download. O link estará disponível numa atividade da plataforma para vocês. E eu vou só sobrescrever e mandar substituir. Agora o meu logo é o do Alura Tracker.

[05:34] Agora com o logo disponível, como eu faço para a minha barra lateral acessar esse logo que está dentro da pasta “assets”? Eu posso fazer um caminho relativo. Se eu estou dentro da pasta de componentes eu tenho que voltar um nível, entrar em “assets” e achar o arquivo.

[05:52] Então para isso fazemos ”../assets/logo.png”. Agora vamos adicionar um pouco de estilo. Eu vou pegar também já pronto para não precisarmos gastar muito tempo digitando o CSS.

header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}COPIAR CÓDIGO
Então o que precisamos é essa porção, então são duas coisas que vamos adicionar.

[06:29] No nosso header adicionamos uma cor de fundo, com o tamanho máximo disponível para ele. Repare que ele já estará disponível dentro de uma coluna. A largura vamos deixar como toda a largura da tela.

[06:45] E no caso do mobile queremos que ele tenha uma altura automática ao invés de preencher tudo, para conseguirmos colocar uma parte da aplicação embaixo da outra.

[06:57] E a última parte que precisamos definir é exportar a função que define este componente. Então primeiro vamos fazer o import da função: import { defineComponent } from ‘vue’.

[07:17] E agora sim já estamos prontos para fazer o export: export default defineComponent. O “defineComponent” vai receber um objeto de configuração, e inicialmente só vamos dizer o nome desse componente: name: ‘BarraLateral’.

[07:38] Então criamos o nosso componente. Mas precisamos de alguma forma colocá-lo disponível. Vamos chamar o <BarraLateral />. Nós queremos que esse componente seja renderizado. Vamos salvar e ver se isso funciona.

[07:57] Agora vou na minha aplicação da Alura Tracker. Repare que está tudo em branco. Temos a barra lateral, que não tem nada.

[08:09] Precisamos, de alguma forma, dizer para o Vue que o componente App terá acesso ao componente da barra lateral. Então vamos fazer import BarraLateral from ‘./components/BarraLateral.vue’.

[08:29] Além disso, precisamos adicionar na propriedade que tem o espaço de configuração para o “defineComponent”, que é justamente componentes. Ou seja, são os componentes relacionados a esse componente. Estamos compondo componentes com outros componentes. E vamos passar a barra lateral.

[08:52] Eu vou salvar e vamos dar uma olhada agora para ver se isso funciona. Agora sim ele já está disponível para nós. A única coisa que está faltando é definirmos o restante da aplicação, que é o nosso formulário e a nossa lista de tarefas.

[09:16] Nossa barra lateral já está pronta, e ficou faltando só adicionar um pequeno padding interno. Então no nosso header vamos fazer padding: 1rem. E vamos voltar para a aplicação. Agora sim, podemos seguir para o formulário.

[09:37] Vamos criar o nosso novo componente, chamado “Formulario.vue”. Já sabemos que a primeira porção é responsável pelo template, pelo layout, o nosso código HMTL. E vamos usar um componente do Bulma chamado “box”, então vou criar uma div com a classe box, <div class=“box”>.

[10:06] Dentro desse box precisaremos dividir de novo o layout em colunas. Então vamos colocar <div class=”columns”>.

[10:16] Na primeira coluna precisaremos de um put, então <div class=”columns”>. E em seguida, <div class=”column is-8”>, que é uma outra forma de dividir o tamanho. E queremos que essa porção seja o correspondente a 8 colunas.

[10:48] Como essa div vai ter comportamento de formulário, vamos adicionar uma role, que vai ser form, role=”form”. Além disso, precisamos também do aria-label. E dentro vamos descrever o que essa div representa, que é aria-label=“Formulário para criação de uma nova tarefa”.

[11:18] O que precisamos agora é de um input: <input type”text” class=”input” placeholder=”Qual tarefa você deseja iniciar?”>.

[11:45] Agora, logo ao lado teremos uma outra coluna. Só vou pedir para ele dar uma formatada no código. A outra coluna vamos começar também com <div class=”column”>. E teremos a parte responsável por aquele contador que vimos nas primeiras aulas. Ele vai ter um tempo, com horas, minutos e segundos, depois vai ter um play e um pause.

[12:12] Vamos começar pelo tempo. No início ainda não temos comportamento, então vamos adicionar uma section do nosso contador e vamos colocar dentro de um Strong para ficar mais chamativo: <strong>00:00:00</strong>.

[12:30] E precisamos agora dos botões de play e de pause. Vou copiar para não precisarmos ficar digitando esse monte de código HTML e vou pedir para ele formatar para mim.

<button class="button">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>COPIAR CÓDIGO
[12:45] Teremos uma section com o tempo gasto, um button com um ícone dentro. Repara que essas são as classes do Bulma. E depois outro button com outro ícone dentro, de play e stop.

[13:00] Vamos salvar e importar no nosso “App.vue”. Antes disso precisamos exportar. Então vou abrir a tag script e colocar <script lang=”ts”>.

[13:24] E vamos fazer import { defineComponent } from ‘vue’. E depois export default defineComponent({}) essa é uma função que recebe um objeto de configuração.

[13:44] E aqui podemos começar pelo nome: name: ‘Formulário’, que é nosso componente responsável pelo formulário. Vamos salvar e agora sim entrar no nosso “App.vue”. E já sabemos como importar nosso formulário. Então só vou aqui, digitar de uma vez só, BarraLateral não mais, quero agora Formulario.

[14:13] Importamos o formulário, definimos como um componente. E podemos finalmente adicionar um formulário. Vamos salvar e dar uma olhada para ver como ficou.

[14:28] Ele está do jeito que esperávamos. Só ficou faltando dar uma organizada interna no nosso componente. Vou pegar as classes da Bulma que quero que fiquem lado a lado.

[14:52] No meu formulário vou arrumar para ficar tudo lado a lado. Vou colocar isso dentro de uma div. Vou adicionar as classes do Bulma. Basicamente eu estou dizendo que quero display flex, quero alinhar os itens no centro com espaçamento entre eles.

[15:34] Agora posso pegar o que está abaixo e jogar dentro dessa div. E vou pedir para ele formatar, formatou e vou salvar.

[15:45] Agora está do jeito que gostaríamos. Já temos um formulário em que podemos colocar uma tarefa “Iniciar os estudos em Vue.js”, por exemplo.

[15:56] Só que os nossos botões ainda não têm comportamento. Está na hora de colocarmos esse cronômetro para funcionar.

https://bulma.io/documentation/

https://fontawesome.com/

@@06
Cronometrando tarefas

[00:00] Nosso formulário já está certo. Agora precisamos adicionar vida ao cronômetro. Ou seja, precisamos que esse cronômetro comece a contar quantos segundos, minutos e horas decorreram desde que o usuário clicou no botão de “Play”, até ele finalizar com o “Stop”.
[00:22] Agora esse componente que até agora era só visual começará a ter comportamento. E como definimos o comportamento em componente Vue?

[00:32] Vamos no nosso formulário. Na nossa função “defineComponent” podemos passar várias informações relacionadas ao nosso componente e o que ele é capaz de fazer.

[00:49] E uma dessas informações são os métodos. Ou seja, são as funções que ele é capaz de executar dada a interação do usuário. Primeiro queremos iniciar a contagem, e também queremos finalizar a contagem:

[01:10] Repara que passamos uma propriedade methods. É essa a propriedade que o defineComponent espera. E dentro podemos passar quantos comportamentos nós quisermos que esse componente será capaz de executar.

[01:25] De início queremos só fazer um console log. Então console.log(‘iniciando’); e também console.log(‘finalizando’);.

[01:40] Então quando o usuário iniciar vamos fazer um console.log(), vai aparecer que está iniciando, e um console.log() também finalizando.

[01:47] O que está faltando agora é dizer quando esses métodos têm que ser executados. E o que queremos é dado um clique executar esse método.

[01:58] Para fazer isso no Vue, vamos entrar no nosso HTML, no template, no button, e colocar @click. Isso quer dizer que todas as vezes que o evento de click for acionado, ou seja, quando o usuário clicar, queremos passar o método que vai ser executado.

[02:17] Vamos passar o método iniciar. E depois, quando o botão de finalizar for clicado, vamos finalizar.

[02:27] Então fizemos os links dos nossos comportamentos com as interações do usuário. Vamos testar e ver se isso funciona. Vou atualizar a página do Alura Tracker. Vou clicar em “Play”. Ele aparece que está iniciando. E ao clicar no “Stop” aparece o finalizando.

[02:51] O que precisamos agora é de alguma forma começar a contar os segundos. Vamos começar definindo um estado inicial para o nosso componente.

[03:00] Para isso temos o método data, que tem que retornar um objeto que representa quais são as informações pertinentes para esse componente. O que queremos é um tempo em segundos, que comece com 0, comece zerado.

[03:28] E então, de alguma forma, quando o usuário iniciar queremos começar a contagem, ou seja, passou um segundo mais um, passou mais um segundo e ele incrementa e assim por diante.

[03:44] E utilizando o JavaScript nós temos um método pronto para utilizar, chamado setInterval. Esse método vai receber dois parâmetros. O primeiro é o que de fato queremos fazer, então vamos passar uma arrow function vazia.

[04:04] E o segundo parâmetro é o intervalo de tempo que precisa ser calculado antes de ele ser executado novamente, em milissegundos. Temos que 1 segundo é igual a 1000 milissegundos. Então se queremos executar uma contagem a cada 1 segundo, vamos passar 1000. Ou seja, a cada 1 segundo ele vai ficar executando esse código.

[04:35] Repara que eu vou colocar mais um console log inicialmente para ’incrementando o contador’. Vou salvar e vamos ver se isso funciona. Lembrando que o setInterval é do JavaScript, ele não é do Vue.

[04:57] Vamos no Alura Tracker, vou atualizar a página e clicar em “Play”. Repara que ele já está contando para nós. Aparece um número indicando o número de vezes que ele imprimiu no console.

[05:14] É isso que queremos. Ao invés de imprimir no console eu quero que a cada 1 segundo ele vá no tempoEmSegundos. Eu tenho o this porque é este componente com essa propriedade.

[05:37] Com isso, passa um segundo e incrementa 1 e assim por diante. E para vermos isso acontecendo, ao invés de deixarmos o tempo zerado, vamos imprimir o tempo decorrido. Para isso usamos duas chaves e passamos o {{ tempoEmSegundos}}.

[06:04] Vou salvar e voltar no Alura Tracker. Repare que ele não vai mais estar no formado hora, minuto e segundo. Vamos testar para ver se isso funciona. Ele ainda está incrementando o contador, está faltando atualizar a página.

[06:32] Repare que agora ele está contando quantos segundos decorreram a partir do usuário ter iniciado a nossa contagem.

[06:43] Só que não queremos saber um tempo em segundos. Nós queremos um tempo mais humano. Até 60 segundos nós entendemos, mas quando passar disso o usuário teria que ficar calculando quanto tempo passou em um total de segundos, e não é isso que queremos.

[07:04] Vamos alterar agora para exibirmos no formato certo. E vamos utilizar mais JavaScript para fazer isso.

[07:13] A primeira coisa que vamos fazer é dizer que queremos uma informação dinâmica. Baseado no tempo em segundos essa informação vai ser computada.

[07:28] Então vamos usar o computed, que vai monitorar uma informação, e conforme essa informação for alterada ele vai reagir e vai se atualizar.

[07:42] E como faremos para calcular esse tempo decorrido? Vamos colocar tempoDecorrido. Para declararmos uma propriedade computada declaramos uma função. E queremos de alguma forma retornar alguma coisa parecida com “00:00:00”.

[08:07] E o que podemos utilizar com as APIs de data do JavaScript para fazer isso? Podemos retornar fazendo um novo objeto de data: return new Date().

[08:21] Vamos fazer isso no console rapidamente para entender como isso funciona. Podemos fazer new Date(). E eu quero pegar um formato mais próximo do que o humano entende. Para fazer isso eu tenho toISOString.

[08:37] Repare que temos exatamente o formato que queremos em uma porção. Não estamos interessados na data e nem nos microssegundos, nem em timezone. Queremos só o pedaço de horas, minutos e segundos.

[08:54] Nós podemos fazer um corte. Podemos chamar o método substr(), que vai recortar para nós. E a partir da posição 11 nós queremos 8: substr(11,8). Então já temos uma forma de pegar a data formatada bem simples.

[09:12] Vamos copiar isso e jogar no nosso código. Só tem um detalhe: o newDate só me dá a data daquele minuto. Eu não quero que seja o tempo atual. Eu quero que seja baseado no cálculo do “tempoEmSegundos”.

[09:33] E o construtor da data tem um método que recebe uma quantidade de milissegundos que representa uma data.

[09:44] Para conseguirmos atingir isso é só pegarmos o this.tempoEmSegundos * 1000. Lembrando que estamos utilizando o TypeScript. Esse método vai retornar uma string, vai pegar o tempo em segundos, multiplicar por 1000 para termos um tempo em milissegundos, e só estamos interessados na porção relacionada a hora, minuto e segundos.

[10:25] Vamos ver se isso funciona. Vou salvar e atualizar a página do Alura Tracker, vou dar “Play”. Ele ainda está mostrando o tempo em segundos. Eu não quero mais mostrar o tempo em segundos, eu quero mostrar o tempo decorrido.

[10:48] Repare que eu não vou executar uma função, eu só estou chamando o tempo decorrido, porque o Vue sabe que por baixo dos panos o “tempoDecorrido” vai funcionar como se fosse uma propriedade do estado do componente, só que calculado. Então nós o definimos como método, porém acessamos como uma propriedade.

[11:09] Vamos ver se isso funciona. Eu vou atualizar para testarmos de novo. Está zerado. Dei o play e ele vai começar a contar. Agora já temos o nosso cronômetro iniciando. E precisamos de alguma forma pará-lo quando o usuário clicar no “Stop”.

@@07
Limpando os intervalos

[00:00] Nosso cronômetro já está contando o tempo do jeito que deveria. Porém, está faltando finalizarmos esse componente.
[00:09] Olhando o nosso código, o que queremos é de alguma forma limpar esse intervalo, setInterval(),e dizer para o TypeScript parar de executar isso, porque eu não preciso mais.

[00:22] Já temos uma forma nativa de fazer isso. Na assinatura do método setInterval ele vai retornar um número, que é o ID que representa aquele intervalo. Então podemos guardar uma referência para ele.

[00:41] Vamos começar dizendo uma referência para o nosso cronômetro: cronometro: 0. E quando iniciamos, podemos gravar a referência nessa propriedade, então temos o cronômetro executando. E para fazermos ele parar de executar, só precisamos limpar esse intervalo com o método clearInterval().

[01:23] É isso que esse método faz. Nós vamos passar um ID para o intervalo e ele vai parar de executar. Então clearInterval(this.cronometro). E agora, quando o usuário clicar em finalizar ele vai limpar esse intervalo, ou seja, ele vai parar de executar isso.

[01:42] Vamos testar. Vou salvar e atualizar a página do Alura Tracker. Vou dar “Play” e ele vai começar a contar. Se eu clicar no botão de “Stop”, ele para de contar. É exatamente isso que queríamos.

[01:58] Só que o que precisamos evoluir agora é o seguinte: além de parar o cronômetro quando o usuário clicar em “Stop”, queremos pegar essa tarefa que está sendo executada, por exemplo, “Estudando Vue.js” queremos parar, limpar esse input e salvar isso em alguma lista. Precisamos enviar isso para algum lugar e guardar na nossa lista de tarefas executadas, e não só usar o cronômetro que o usuário possa fazer play e pause quando ele quiser.

[02:34] Precisamos de alguma forma colocar esse formulário para se comunicar com o nosso App, precisamos de uma lista de tarefas. Quando o usuário finalizar, queremos popular essa lista de alguma forma.

[02:52] E outra coisa que já podemos dar uma olhada é que esse componente já está ficando grande demais, ele está com responsabilidades demais. Talvez possamos começar a refatorar. Todo o formulário está fazendo a parte de tempo, ou seja, além de um formulário ele também é um temporizador e tem um cronômetro. Está muito grande, com muita responsabilidade. Talvez seja interessante quebrá-lo em componentes menores. Então fica a dica do que vem pela frente.

@@08
Corrigindo o bug

Uma pessoa desenvolveu um componente que implementa uma técnica chamada pomodoro, que consiste basicamente em emitir um alerta a cada 15 minutos, marcando uma pausa para um intervalo. Porém, quando o usuário pede para finalizar o pomodoro, o componente não está funcionando como deveria.
Esse é o código desenvolvido:

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  // código omitido
  data() {
    return {
      intervalo: 0,
    };
  },
  methods: {
    iniciar(): void {
      const minutos = 15 * 60 * 1000;
      this.intervalo = setInterval(() => {
        alert("Hora de fazer um intervalo!");
      }, minutos);
    },
    finalizar(): void {
      this.intervalo = null;
    },
  },
  // código omitido
});
</script>
COPIAR CÓDIGO
Selecione uma alternativa

O correto seria utilizar o delete, assim: delete this.intervalo.
 
Alternativa correta
O correto seria definir o this.intervalo como zero.
 
Alternativa correta
O correto seria executar clearInterval(this.intervalo).
 
Alternativa correta! Exatamente! Para encerrar um código que está sendo executado a cada X milissegundos, passamos identificador para a função clearInterval().

@@09
Faça como eu fiz

Praticar ajuda bastante no aprendizado de um novo conceito. Assim, é muito importante que você implemente o que foi apresentado nesta aula.

Não deixe de sanar suas dúvidas antes de dar continuidade ao curso. Estaremos te esperando no fórum da Alura caso alguma dúvida surja.

@@10
O que aprendemos?

Nessa aula, você aprendeu:
Iniciar um projeto novo, utilizando TypeScript e Vue3;
Aprendemos como instalar e utilizar o vue cli para construir um novo projeto, customizando inclusive as dependências que teremos.
Importar o Bulma;
Fazendo uma única importação, no index.html, passamos a ter disponível todos as facilidades desse framework CSS.
Criar componentes;
Para cada novo componente, criamos um arquivo Vue com as seguintes sessões: template, para o html. script, para o comportamento e style para o visual.
Escutar eventos de clique;
O Vue nos ajuda a trabalhar com eventos, basta utilizarmos a sintaxe @NOMEDOEVENTO direto no elemento que queremos ouvir.
Trabalhar com intervalos.
O setInterval é perfeito para nosso cenário, de incrementar o tempo decorrido a cada segundo.

#### 03/02/2024

@02-Compondo componentes

@@01
Projeto da aula anterior

Caso queira começar daqui, você pode baixar o projeto da aula anterior nesse link.

https://github.com/alura-cursos/alura-tracker/tree/aula-1

@@02
Refatorando o formulário

Transcrição

[00:00] Nosso cronômetro já está iniciando quando ele precisa. Começa a contar o tempo e quando finalizamos ele para de contar o tempo. Esse é o comportamento desejado para a nossa aplicação.
[00:13] Só que tem um pequeno porém: se dermos uma olhada no nosso código, o nosso formulário está muito extenso e está com um monte de responsabilidades.

[00:24] Ele precisa mostrar o tempo decorrido, transformar o tempo decorrido em segundos para o formato que queremos, ouvir os eventos de play e stop.

[00:33] Então precisamos começar a tomar um pouco de cuidado para ele não crescer demais. E como vamos começar a resolver esse problema?

[00:43] Podemos pegar uma parte simples, que é justamente a parte responsável por mostrar o tempo em segundos formatado e extrair para outro componente. Então vamos começar a fazer isso.

[00:57] Precisamos de um visual de cronômetro. Então vamos criar nosso componente cronômetro. Já sabemos como fazer “Components > New File”, escrever “Cronometro.vue”. Já sabemos que o nosso HTML é o template, então basta só darmos um “Ctrl + X” para tirar do formulário e um “Ctrl + V” para colocá-lo no cronômetro. E vou pedir para ele formatar.

[01:26] Agora precisamos trazer o comportamento dele. Precisamos receber o valor “tempoDecorrido” de alguma forma e formatá-lo. Então vamos para o nosso script. Ficou duplicado, vou só ajustar, vamos ajustar o nosso import. Queremos o “defineComponent” direto do Vue. E vamos direto dar o nome para o nosso componente, que vai ser “Cronometro”:

[02:07] Agora precisamos de alguma forma receber esse “tempoDecorrido” e formatá-lo. Para formatar já sabemos como fazer, já está pronto. É só mover o “computed” do formulário e colocar no cronômetro. Então além do name ele terá a propriedade computada “tempoDecorrido”.

[02:37] Agora o que está faltando é receber esse tempo em segundos. Precisamos de alguma forma pedir para o nosso componente pai informar o tempo que passou em segundos.

[02:51] Como definimos esse tempo em segundos? Nós vamos criar uma outra propriedade. Tudo que vamos receber do componente pai vai ficar dentro da nossa propriedade props. Como o próprio nome já diz, props são as propriedades que vamos receber nesse componente.

[03:12] Para definir isso precisamos dizer qual é o nome da propriedade, que vai ser tempoEmSegundos:. E como vamos configurar essa propriedade? Queremos dizer qual é o tipo e qual é o valor padrão.

[03:32] O tipo dessa propriedade é um valor numérico, é um número inteiro que representa a quantidade de segundos decorrida, então type: Number,.

[03:42] E além disso podemos definir um valor padrão, então default: 0. Então por padrão esse tempo decorrido será 0.

[03:52] Agora já trouxemos todo o comportamento, a formatação de data para cá. Usamos o mesmo nome, então continua funcionando, this.tempoEmSegundos quer dizer essa propriedade tempoEmSegundos aqui.

[04:04] O que queremos é no nosso formulário usar esse componente. Então no formulário vamos colocar <Cronometro />. Só que precisamos importar e registrar esse componente, o que já sabemos como fazer. Então na parte de baixo vamos fazer import Cronometro from ‘./Cronometro.vue’.

[04:35] E para finalizar precisamos indicar que esse cronômetro é um componente filho, então components: { Cronometro }. Importamos o cronômetro, definimos como componente filho e importamos. Vamos salvar e ver se isso funciona.

[04:58] Vou voltar aqui na minha página, ele está reclamando do modo como estamos começando o componente. Ficou um sinal de maior duplicado, então vou arrumar e salvar.

[05:21] Vou atualizar. E agora ele está falando que não está entendendo a parte : string. Por que isso aconteceu? Na hora que definimos o nosso componente nós lançamos a tag script, mas não definimos o lang, que é o TypeScript. Então fica <script lang=’ts’>. Vou salvar.

[05:51] Vamos olhar agora. Está funcionando e está exibindo inclusive o valor padrão. Vamos dar o play. Nada aconteceu. Para esse cronômetro incrementar conforme o tempo for passando, precisamos indicar no formulário que esse cronômetro vai ter uma propriedade chamada “tempoEmSegundos”, que está relacionada com o “tempoEmSegundos” que está de fato sendo contado.

[06:24] Então agora passamos o nosso valor de tempo em segundos via prop para o componente cronômetro. Então ele espera um tempo em segundos também. Vou salvar o formulário e vamos voltar para o Alura Tracker.

[06:39] Agora ele já está até funcionando, porque ele fez o hot reload, ou seja, na hora que eu salvei ele já atualizou o componente e agora ele está recebendo o valor que o formulário passa para ele.

[06:54] Vamos olhar o código de novo. Nós continuamos com o nosso comportamento de iniciar e finalizar e passamos o “tempoEmSegundos” para o cronômetro. Então nosso cronômetro recebe o tempo em segundos.

[07:10] Dado o tempo em segundos, ele vai transformar daquele mesmo jeito que fazíamos antes: transformar isso num objeto de data, pegar a string e recortar só o pedaço que queremos representando quantas horas, minutos e segundos passaram. Vamos continuar agora melhorando o nosso sistema.

@@03
Evoluindo o temporizador

[00:00] Já refatoramos o código do nosso cronômetro. A porção responsável por mostrar o tempo decorrido já foi refatorada, mas precisamos melhorar um pouco mais a experiência do desenvolvedor.
[00:13] O nosso formulário, apesar de já estar um pouco menor porque já extraímos a lógica de exibição do cronômetro, ainda está muito grande. Temos todo o controle de tempo, todo esse temporizador de iniciar e finalizar. Essa responsabilidade ainda está dentro do formulário.

[00:32] Então vamos dar mais uma refatorada, vamos extrair mais um componente, que é justamente toda essa parte aqui que vai controlar o iniciar, o finalizar e o tempo decorrido.

[00:43] Já vou dar um “Ctrl + X” para tirar isso. Vou criar um componente novo chamado “Temporizador.vue”. Já sabemos como é o template. Já temos nossa div com o cronômetro, o iniciar e o finalizar.

[01:06] Agora precisamos trazer toda a lógica que está no formulário. Então vamos copiar tudo que vamos reaproveitar do formulário e colar no temporizador. Vou começar ajustando o nome do componente, mudando de “Formulário” para “Temporizador”.

[01:26] O import do cronômetro já está correto, os dados já estão corretos. Nosso método de iniciar e finalizar também. Então vou salvar e agora podemos tirar tudo que ficou por responsabilidade do temporizador.

[01:51] Repara que o nosso formulário está bem mais limpo. A lógica de comportamento está bem menor. E o HTML também, porque agora ele vai ter só o temporizador. Já ficou bem mais enxuto e coeso o nosso formulário. Vamos ver se essa nova refatoração está funcionando. Vou atualizar a página do Alura Tracker.

[02:15] Se eu der um “Play” ele vai começar a contar. Se eu mandar parar ele para a contagem. O comportamento continua exatamente como era antes. Só que agora já melhoramos a experiência do desenvolvedor.

[02:28] E vamos agora para a experiência do usuário. Repare que os botões estão habilitados o tempo todo. Então o usuário pode vir aqui e clicar muito rápido, cliquei várias vezes no botão de “Play”, o cronômetro fica tudo doido, porque tem vários intervalos agora incrementando o nosso tempo em segundos. E não é isso que queremos.

[02:51] Nós queremos deixar o botão de “Play” habilitado se o cronômetro está parado. E se ele estiver rodando, queremos desabilitar o “Play”. E o contrário para o “Stop”. Ele só pode ficar habilitado se o cronômetro estiver rodando, e se ele estiver parado o “Stop” tem que estar desabilitado.

[03:09] Então vamos criar esse controle no nosso temporizador. Vou criar uma nova propriedade dentro do meu estado. Vou chamar de cronometroRodando: false.

[03:20] Estou iniciando como false, ou seja, se o cronômetro não está rodando, eu quero desabilitar o meu botão de “Stop”.

[03:33] Então no meu botão de “Stop” vou criar o nosso atributo linkado com esse “cronometroRodando”: disabled=”cronometroRodando”.

[03:43] Só que esse atributo tem que se linkar com o meu estado. E para fazer isso no Vue eu adiciono dois pontos na frente. Com isso ele sabe que o valor do atributo está linkado com o meu estado. Então se o meu cronômetro não está rodando, eu não posso finalizar, então fica :disabled=”!cronometroRodando”.

[04:07] Vou salvar e vamos ver se isso funciona. Repara que eu já não consigo finalizar quando o cronômetro está parado.

[04:15] Agora precisamos fazer a lógica inversa: se eu iniciá-lo, eu preciso inverter essas propriedades. Quando eu iniciar o meu cronômetro, eu vou dizer que this.cronometroRodando = true. E logo quando finalizar, this.cronometroRodando = false.

[04:46] Então quando eu inicio ele é true e quando eu finalizo ele é false. Vamos ver se agora quando eu inicio ele já troca o atributo de desabilitado. Atualizei e dei o “Play”. E ele já habilitou o “Stop”, mas faltou travar o “Play”.

[05:09] Então no meu button de iniciar, vamos colocar :disabled=”cronometroRodando”. Então se o cronômetro está rodando, ele está desabilitado. E vou salvar.

[05:28] Vou voltar para a minha página e vou recarregar. O cronômetro está parado, então posso iniciar, mas não posso finalizar. Se eu iniciar, automaticamente ele já troca e eu posso finalizar, mas não posso iniciar novamente.

[05:45] Agora sim, tanto a experiência do desenvolvedor quanto a do usuário estão bem bacanas. Agora, quando o usuário finalizar a tarefa, temos que colocar isso em alguma lista para que comecemos a exibir todas as tarefas finalizadas.

[06:03] Vamos agora adicionar esse comportamento de comunicação entre componentes.

@@04
Para saber mais: Olhando a Date API mais de perto

O objeto de data é muito poderoso, e hoje em dia ele faz muitas coisas que facilitam o nosso dia a dia. Vale a pena conhecer mais para tirarmos proveito de todas os métodos que ele nos disponibiliza. Confira aqui.

@@05
Code review

Maia precisa emitir um evento que informa as horas, no formato HH:mm:ss mas está com dificuldade para formatar a data:
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  // código omitido
  emits: ['aoSolicitarHora'],
  methods: {
    informarHora () : void {
      this.$emit('aoSolicitarHora', new Date())
    }
  }
  // código omitido
});
</script>COPIAR CÓDIGO
Além da ISO string que utilizamos, o objeto de data possui uma outra forma de formatar somente as horas, minutos e segundos. Qual seria?

new Date().toISOString()
 
Esse método retorna uma string respeitando a ISO.
Alternativa correta
new Date().toLocaleTimeString()
 
Alternativa correta! Exatamente! Esse método já retorna o horário, localizado de acordo com o idioma do navegador. Saiba mais sobre ele aqui.
Alternativa correta
new Date().toLocaleDateString()
 
Esse método retorna uma representação em string de parte da data dada a instância Date de acordo com as convenções específicas do idioma. Saiba mais sobre ele aqui.

https://en.wikipedia.org/wiki/ISO_8601

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleTimeString

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleDateString

@@06
Eventos e props

[00:00] Nosso controle de tempo já está funcionando exatamente como ele precisava funcionar. Conseguimos iniciar, ele começa a contar e então finalizamos.
[00:10] E agora precisamos fazer duas coisas. A primeira delas é que quando o temporizador for finalizado nós precisamos avisar o formulário que o usuário finalizou. E quando o usuário finalizar o tempo, o formulário em si precisa juntar as informações de tempo com o input com o nome da tarefa e passar isso adiante.

[00:35] Então são duas comunicações que precisamos fazer. Vamos começar definindo o comportamento do nosso temporizador.

[00:44] Para fazer isso utilizando o Vue, nós vamos indicar no nosso defineComponent, o método que configura o nosso componente e o exporta, que o nosso componente vai emitir um evento. Ele vai emitir alguma coisa em determinado momento.

[01:05] Ele tem uma propriedade chamada emits, que é justamente uma lista de eventos que esse componente é capaz de emitir.

[01:14] E o primeiro deles que queremos indicar é o seguinte: emits: [‘aoTemporizadorFinalizado’]. Ou seja, quando o tempo for finalizado nós vamos fazer alguma coisa.

[01:29] E queremos fazer isso logo após o usuário finalizar. Nós já definimos que esse componente emite esse evento e agora queremos de fato emiti-lo só quando o usuário finalizar.

[01:45] Para emitir esse evento, ou seja, para o temporizador avisar para o pai dele que o evento foi emitido vamos fazer this.$emit, que é um método que recebe dois parâmetros.

[02:06] O primeiro parâmetro é o nome do evento que ele está emitindo, justamente o ('aoTemporizadorFinalizado',).

[02:14] O segundo parâmetro é o payload, é a carga de dados que vai junto, que quem estiver ouvindo o evento será capaz de receber, que é o nosso tempoEmSegundos, ('aoTemporizadorFinalizado', this.tempoEmSegundos) .

[02:30] E repara que quando o tempo for finalizado, ou seja, aquela tarefa for finalizada, também vamos precisar liberar o temporizador para a próxima tarefa. Para isso vamos dizer que this.tempoEmSegundos = 0, ou seja, vamos resetar.

[02:48] Quando o usuário finalizar ele não vai dar play e pause, ele vai finalizar. Vamos salvar e ver se continua funcionando.

[02:59] Vou atualizar a página do Alura Tracker. Iniciei, o tempo está contando. Finalizei e ele zerou o cronômetro para mim.

[03:08] Mas está faltando fazer alguma coisa com essa informação. Precisamos agora no formulário ouvir esse evento.

[03:19] Nós já fizemos isso antes com um evento padrão. Repare que ouvimos o evento de clique dentro do temporizado. Quando o usuário clica no botão de iniciar ou finalizar começamos a fazer alguma coisa.

[03:37] Para tratarmos com os nossos eventos customizados, que nós criamos, é bem parecido. Então no formulário vamos dizer que queremos ouvir um evento, então usamos o arroba. Então vamos fazer <Temporizador @aoTemporizadorFinalizado=”finalizarTarefa”/>.

[04:11] Quando o temporizador for finalizado, queremos finalizar a tarefa. Então vamos criar agora esse método na parte de baixo: methods: { finalizarTarefa () { } }.

[04:31] No nosso evento customizado estamos enviando o tempo em segundos. Então queremos receber isso: methods: { finalizarTarefa (tempoDecorrido: number) { } }.

[04:50] E o “finalizarTarefa” é um método que não retorna nada, então fica methods: { finalizarTarefa (tempoDecorrido: number) : void { } }. O nosso método não vai finalizar nada, ele vai receber o tempo decorrido. Então vamos fazer um console.log(‘tempo da tarefa’, tempoDecorrido).

[05:20] Vamos salvar e ver se isso funciona. Vou atualizar a página no navegador. Vou iniciar e ele vai começar a contar. Vou dar um stop e ele deu que o tempo da tarefa é 3. Ele até já identifica que é um número, e o tempo da tarefa foi o tempo que mandamos imprimir.

[05:43] Agora junto com isso precisamos capturar o valor indicado pelo usuário no texto do input. Então quero linkar esse cara com um estado do componente. Vamos usar a propriedade v-model, que será responsável por linkar com o nosso estado a descrição da nossa tarefa: v-model=”descricao”.

[06:12] Dado um input que meu usuário digitou, eu quero linkar com o meu estado. E agora preciso declarar esse estado. Então vou usar o data, que é o método que retorna o estado: data ( ) { return { descricao: ‘ ‘}. Então ele retorna um objeto que tem uma descrição que começa vazia.

[06:33] Então linkamos o valor da variável descrição do estado com o que o usuário digitou. Então além de pegar o tempo decorrido vamos pegar o nome da tarefa: console.log(‘descrição da tarefa’, this.descricao).

[06:59] Vamos ver se conseguimos linkar todos os valores envolvidos para o nosso formulário, o nome, a descrição da tarefa e tempo decorrido.

[07:09] Então vou atualizar a página do navegador e colocar como exemplo “Estudar Vue.JS”. Vou dar “Play” e ele vai começar a contar. Dei um “Stop” e o tempo da tarefa foi de 2 segundos e a descrição da tarefa foi “Estudar Vue.JS”.

[07:29] Assim como precisamos zerar o formulário, também precisamos zerar o input para liberá-lo para a próxima tarefa. Então vamos fazer isso.

[07:39] Depois de fazer o console.log vamos dizer que a descrição será vazia, ou seja, eu quero limpar o input para a próxima tarefa. Vou salvar e voltar para o navegador, recarregando a página.

[07:54] Vou inserir “Estudando TS”. Vou iniciar, o tempo vai começar a contar, vou finalizar e ele limpou o input e logou no console para nós o tempo e a descrição da tarefa.

[08:10] E agora o formulário, por sua vez, precisa passar essa tarefa adiante, para alguém que vai controlar a lista. Não é responsabilidade do formulário controlar essa lista. Ele sabe quando uma tarefa foi finalizada e ponto. Essa é a responsabilidade dele.

[08:28] Então temos que começar a pensar agora em para onde essa tarefa vai, como vamos identificá-la e aonde vamos armazená-la. Precisamos começar a trabalhar com listas.

##### 03/02/2024

@03-Trabalhando com listas

@@01
Projeto da aula anterior

Caso queira começar daqui, você pode baixar o projeto da aula anterior nesse link.

https://github.com/alura-cursos/alura-tracker/tree/aula-2

@@02
Completando uma tarefa

[00:00] Agora que nosso formulário já está pronto para enviar uma tarefa nova, o que precisamos é deixar o nosso HMTL, nosso template, nossa marcação pronta para receber essa lista de tarefas.
[00:15] Vamos entrar no nosso “App.vue”, e onde nós deixamos um espaço reservado queremos de alguma forma ter uma lista de tarefas. E dentro dessa lista, dessa div, nós queremos várias tarefas.

[00:35] Precisamos de um componente que represente uma tarefa. Então vamos começar a criar esse componente novo. Vou criar um novo arquivo chamar “Tarefa.vue”.

[00:51] Já podemos ir para o nosso template. Dentro desse componente teremos uma div que terá um box, que é uma classe do Bulma. Ela vai ter uma cor, um sombreamento.

[01:09] Além disso, vou pegar da documentação que eu tenho e trazer para o Vue. Eu quero que tudo dentro desse box tenha negrito, então coloco has-text-weight-bold, ou seja, tudo ali dentro terá o texto mais forte. E logo em seguida podemos dividir em duas colunas, então usamos o <dic class="columns">.

[01:32] A coluna da esquerda vamos fazer com um espaço maior para a descrição do que para o temporizador, <div class="column is -7">. Dentro dessa div vai ser a descrição da tarefa. E na outra coluna precisamos colocar aquele formato de tempo decorrido, <div class="column">. Só que já temos um componente pronto para isso, que é o que vamos inserir, <Cronometro />.

[02:13] Vamos fazer agora o import do Cronometro: <script lang=”ts”> import { defineComponent } from ‘vue’.

[02:36] E depois vamos fazer export default, que é o resultado da função defineComponent que recebe o nosso objeto de configuração. E já vamos dizer que o nome desse componente será “Tarefa”: export default defineComponent ( { name: ‘Tarefa’ } ).

[02:57] Agora já temos a base pronta. Está faltando importar o cronômetro. Vamos fazer import Cronometro from ‘./Cronometro.vue’. E também falta adicioná-lo à lista de componentes, então componentes: { Cronometro }.

[03:23] Temos a descrição da tarefa e o cronômetro. Lembrando que o cronômetro recebe uma propriedade, que é a tempoEmSegundos, que inicialmente será de 15 segundos, por exemplo, .

[03:41] Vamos salvar. E agora no “App.vue” vamos importar o Tarefa. Vamos adicionar na nossa lista de componentes. E agora sim devemos ter alguma lista de tarefas já pronta. Vamos ver como isso ficou.

[04:02] Repara que ele já trouxe uma lista, com tudo funcionando como queríamos, com o texto em bold, usando já o cronômetro para formatar o tempo decorrido.

[04:11] Agora vamos voltar na nossa lista. Temos nossa classe lista e vamos colocar um padding para ficar um espaçamento um pouco mais agradável.

[04:29] Estamos recebendo uma notificação de erro no console do navegador de que ele esperava um número e nós passamos uma string. Depois nós resolvemos isso.

[04:34] Agora a última coisa que está faltando é adicionar uma cor de fundo para o nosso box que representa uma tarefa. Eu vou pegar o código hexadecimal da cor que eu coloquei na minha cola. E no nosso “Tarefa.vue” vamos criar a nossa tag de estilo.

[04:56] Lembra que quando dizemos que esse estilo é escopado nós estamos dizendo que ele só será aplicado nesse componente específico, ou para os filhos dele. Queremos que o nosso box tenha um background do hexadecimal que eu peguei, que é o #FAF0CA, <style scoped> .box {background: #FAF0CA;} </style>.

[05:20] Agora ficou do jeito que precisávamos. Só que ela ainda é uma lista estática. O que queremos é que quando o usuário digitar uma tarefa aqui no campo de texto, por exemplo, “Executando a limpeza do HD” vai lá e dá um “Play” e quando ele finalizar queremos que essa tarefa vire uma tarefa dentro dessa lista.

[05:41] Então vamos agora fechar a comunicação entre o nosso formulário e o nosso App para fazer essa lista se tornar viva e dinâmica.

@@03
Trabalhando com listas

[00:00] Agora vamos trazer dinamismo e vida para essa lista de tarefas. Não queremos nada estático desse jeito. O que queremos é linkar uma tarefa finalizada com essa lista de tarefas que será exibida na parte de baixo.
[00:14] De volta ao nosso código, podemos começar criando uma interface que vai representar o que é uma tarefa. Vou criar uma nova pasta chamada “interfaces”, e dentro teremos uma interface “I”, que representa uma tarefa, então “ITarefa.ts”.

[00:39] Agora vamos criar essa interface que vai representar uma tarefa executada. Vamos exportá-la por padrão: export default interface ITarefa. O que representa uma tarefa?

[00:55] Teremos uma duração em segundos que será numérico: duracaoEmSegundos: number,. E também teremos uma descrição que será um texto: descricao: string.

[01:10] O que queremos agora é que nosso “App.vue” tenha uma lista de tarefas. Já sabemos como definir o estado do componente, que é com o método data, que retorna um objeto, e queremos uma lista de tarefas. Essa é uma lista bem específica, que é um array de tarefas, tarefas: [] as ITarefa[].

[01:38] Agora está faltando importar: import ITarefa from ‘./interfaces/ITarefa’. Agora sim ele está importando o que precisamos.

[02:13] O que precisamos agora é que toda vez que um formulário finalizar uma tarefa ela seja salva na lista. Então vamos criar o método que salva uma tarefa: methods: { salvarTarefa }.

[02:30] Ele vai receber uma tarefa por parâmetro, que é a tarefa que queremos salvar: methods: { salvarTarefa (tarefa: ITarefa) { } }. E o que queremos é adicionar no nosso estado, então this.tarefas.push(tarefa).

[03:01] Agora precisamos linkar esse método com o evento do formulário. Então nosso formulário terá um <Formulario @aoSalvarTarefa=”salvarTarefa”/>, queremos que quando a tarefa for salva, queremos executar esse método salvartarefa. Vou salvar, mas esse evento ainda não implementamos aoSalvarTarefa. Então vamos no nosso formulário,“Components > Formulario.vue”.

[03:29] Já na largada vamos dizer que ele emite esse evento, então emits: [‘aoSalvarTarefa’],. É uma array de string de texto com os nomes dos eventos que ele emite. E vamos emitir this.$emit o primeiro parâmetro é o nome do evento e o segundo é o que estamos enviando. Estamos enviando uma tarefa, então precisamos enviar a duração em segundos, que é o “tempoDecorrido”, e ela também terá uma descrição, que está linkada no input:

[04:15] Agora, quando alguém salvar uma tarefa o nosso formulário vai emitir um evento, o app vai ouvir esse evento e adicionar na lista de tarefas. O que está faltando agora?

[04:29] Agora não queremos uma tarefa estática, e sim uma lista dinâmica, que vai crescer conforme a lista de tarefas vai crescendo.

[04:39] Para isso utilizamos a diretiva do Vue v-for, ou seja, para cada tarefa no nosso array de tarefas queremos fazer alguma coisa.

[04:54] Repara que ele já vai dar uma dica. Ele está falando que para você fazer uma iteração desse jeito você precisa linkar uma propriedade chamada key, que vai identificar esse item dentro da lista para o Vue poder saber quando ele vai ou não renderizar aquele componente de novo.

[05:17] Então como não temos banco de dados que vai retornar o ID da tarefa, por exemplo, podemos utilizar o índice dessa tarefa no array. Então vamos pegar o index e usá-lo como chave, <Tarefa v-for=”(tarefa, index) in tarefas” :key=”index”/.

[05:38] Ele já parou de reclamar. E para cada tarefa do nosso array ele vai renderizar. Vamos salvar e ver se isso funciona.

[05:49] Repara que não temos mais uma lista vazia. Vamos testar uma tarefa nova e iniciar. O tempo vai contar, e na hora que fazemos um stop ele já vai inserir uma nova tarefa. Vamos fazer mais uma nova, vamos dar o “Play” e finalizar. E ele traz essa outra tarefa para a lista.

[06:17] Agora, para finalizarmos de vez esse tratamento, essa ideia de lista viva que criamos, precisamos passar uma tarefa para o componente de tarefa. Ou seja, o que queremos não é mais esse componente estático, que sempre exibe a mesma coisa. Nós queremos receber isso via prop.

[06:41] E como definimos uma prop que vamos receber? Podemos fazer props: { tarefa: { } }. O nome dessa prop é tarefa, ou seja, ela é a tarefa que será exibida no nosso componente. O tipo dessa tarefa é objeto type: Object as PropType<ITarefa>. E nós queremos um tipo específico de objeto. Para fazer isso utilizando o Vue vamos adicionar um novo import, que é o PropType.

[07:14] E vamos indicar que essa propriedade que estamos recebendo é desse tipo específico que criamos, que é o ITarefa. Então fica props { tarefa: { type: Object as PropType<ITarefa> } }. Vamos fazer agora o import disso: import ITarefa from ‘../interfaces/ITarefa’.

[07:38] Agora já dissemos qual é o tipo dessa propriedade. E vamos dizer que ela é obrigatória, então required: true. Ou seja, não existe uma tarefa sem essa propriedade.

[07:52] Agora que já estamos recebendo ela por parâmetro, queremos exibir a descrição dela tarefa.descricao. E o “tempoEmSegundos” não será mais 15 fixo. Lembra que quando fazemos um link com uma variável nós colocamos os dois pontos. E, ao invés de 15, vai ser ”tarefa.duracaoEmSegundos”.

[08:23] Agora sim não teremos mais texto estático. Mas precisamos passar isso para o nosso componente. Então vamos dizer que :tarefa=”tarefa”/>, vai ser essa tarefa da vez aqui, ou seja, a tarefa que ele está ali na interação.

[08:43] Vamos salvar e ver se isso vai funcionar. Vou voltar no navegador e atualizar a página. Vamos ver se vai funcionar “Treinando no Alura” vou dar “Play” na tarefa e finalizar. Agora sim ele já está recebendo o texto e a duração exata que foi enviada na hora que salvamos essa tarefa.

[09:11] Então se eu estou “Estudando Vue.js no Alura” damos um play ele vai contar esse tempo, o tempo vai decorrer, o tempo necessário para executar a tarefa, quando o usuário finaliza ele já coloca exatamente como precisamos. Ou seja, agora temos essa lista viva de tarefas, que representa de fato todas as tarefas que o usuário executou.

@@04
Para saber mais: Para que serve o "key" do v-for?

O vue utiliza uma estratégia específica de renderização de listas, e o atributo :key é essencial para o bom funcionamento.
Se quiser saber mais detalhes sobre como a biblioteca funciona por baixo dos panos, confira aqui.

https://v3.vuejs.org/guide/list.html#maintaining-state

@@05
Resolução de problemas

Tigas implementou a lista de tarefas, conforme o exercício, mas gerou um erro. Vamos ajudá-lo com a solução de problemas.
O código que renderiza a lista:

        <Tarefa v-for="(index, tarefa) in tarefas" :tarefa="tarefa" :key="index"/>COPIAR CÓDIGO
O código da prop do componente Tarefa:

  // código omitido
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  },
  // código omitidoCOPIAR CÓDIGO
E o erro:

[Vue warn]: Invalid prop: type check failed for prop "tarefa". Expected Object, got Number with value 0COPIAR CÓDIGO
Selecione uma alternativa

Tigas não configurou corretamente a prop do componente, que deveria ser Number e não ITarefa.
 
Alternativa correta
O índice não deve ser utilizado como :key.
 
O erro não está relacionado com a :key em si.
Alternativa correta
Tigas cometeu um erro comum, e inverteu as variáveis index e tarefa. O correto seria <Tarefa v-for="(tarefa, index) in tarefas" :tarefa="tarefa" :key="index"/>.
 
Alternativa correta! Exatamente! É muito comum no dia a dia invertemos os parâmetros do v-for. O primeiro é o item da lista, e o segundo é o índice do item na lista.

@@06
Renderização condicional

[00:00] Agora já está tudo funcionando como precisamos. Mas tem duas coisas que precisamos resolver para melhorar ainda mais a experiência do nosso usuário.
[00:09] A primeira delas é que o usuário pode executar uma tarefa que não tem uma descrição específica. Então ele vai executar o que tiver que executar e quando finalizar teremos um espaço vazio, faltando uma descrição.

[00:27] Precisamos tratar e colocar uma descrição padrão. Vamos no nosso “Tarefa.vue”. Se a descrição não existe, queremos uma descrição padrão. E podemos usar o nosso operador OU (||). Ou seja, se não existe vamos colocar uma descrição padrão, que será {{ tarefa.descrição || “Tarefa sem descrição”.

[01:06] No JavaScript, quando fazemos um operador OU ele vai retornar o segundo valor. Então é isso que queremos: se essa descrição não existe, vai ficar como uma tarefa sem descrição. Vamos salvar e ver se isso funciona a aplicação.

[01:22] Ele já está adicionando essa descrição padrão. Se o usuário executar uma tarefa sem descrevê-la teremos o nosso “Tarefa sem descrição”.

[01:34] A última coisa que está faltando para melhorar ainda mais essa experiência é essa lista em branco. O que queremos na verdade é colocar um card dizendo que o usuário ainda não executou nenhuma tarefa nesse dia.

[01:49] Então no “App.vue”, quando essa lista estiver vazia queremos exibir um box dizendo que o usuário ainda não executou nenhuma tarefa.

[02:11] Já sabemos como fazer o box, então podemos copiar e colar a div do box. Mas ao invés de fazer isso, nós poderíamos extrair essa pequena porção para um componente que vai representar nosso box.

[02:33] Então ao invés de fazer esse copiar e colar, vamos desistir dessa ideia e vamos criar o componente box, que vai representar aquele quadrado amarelo no qual podemos colocar um texto dentro.

[02:52] Vamos pegar as classes, porque esse componente será bem simples, e criar um novo arquivo chamado “Box.vue”. Ele terá o <template> e o <script lang="ts">, lembrando de colocar o lang. O template basicamente será uma div com a classe onde vai o conteúdo, <div class=”box has-text-weight-bold”>. Só queremos um encapsulador.

[03:31] E no script vamos fazer nosso import padrão: import { defineComponent } from ‘vue’ e export default defineComponent( { name: ‘Box’ } ).

[03:58] Agora é só importarmos o box no “Tarefa.vue”. E agora podemos substituir o <div class=”box has-text-weight-bold”> somente pelo nosso componente Box. Só vamos lembrar de colocá-lo na nossa lista de componentes também.

[04:23] Agora só está faltando mudar a cor do box para o “Box.vue”, então vou copiar e colar o style da cor do background. Agora sim temos o box amarelo que estamos reaproveitando ao invés de fazer “Ctrl + C” e “Ctrl + V”.

[04:40] Vamos ver se isso funciona. Vamos adicionar aqui “Uma nova tarefa”, vamos dar o “play”, começa contar, podemos finalizar. Mas repara, cadê o nosso conteúdo? Nós adicionamos aqui, eu tenho aqui, quero esse conteúdo e colocar ele na minha caixa. Como eu faço isso no Vue? Muito simples.

[05:04] Basta adicionarmos um <slot></slot>. O que queremos dizer com esse slot é que o que estiver dentro do componente será renderizado no Box. Vamos dar uma olhada para ver se funcionou. E continuou funcionando.

[05:25] Agora sim, podemos tratar nosso placeholder. Teremos uma descrição quando o usuário começar a aplicação e ele ainda não executou nenhuma tarefa. No “App.vue” teremos um <Box> e dentro dele vamos colocar um texto “Você não está muito produtivo hoje :(”.

[06:06] Quando a nossa aplicação executar ele tem que exibir essa caixa. Vamos atualizar e ver se isso funciona. Repara que ele até colocou, mas falou que não está conseguindo resolver Box, porque não importamos ele. Então vamos fazer import Box from ‘./components/Box.vue’.

[06:34] Vamos adicionar na nossa lista de componentes e salvar. Agora continua funcionando, só que ele está sem o padding. É bem provável que tenhamos de fora daquela div lista.

[06:46] Foi isso mesmo, vamos subir um nível para cima para ele ficar dentro da lista, daquele padding. Agora sim funciona. Se executarmos uma tarefa qualquer, quando finalizar, apareceu aquela mensagem "Você não está muito produtivo hoje :(", mas não é bem isso. Nós só queremos exibir essa mensagem se a nossa lista estiver vazia. Então vamos fazer essa renderização condicional.

[07:16] Para isso podemos, por exemplo, criar uma propriedade computada, computed: que vai dizer se a listaEstaVazia (): boolean, é sempre um método. Para saber se a lista está vazia vamos ver se o tamanho dela é 0. Então vamos retornar se o tamanho da lista de tarefas é 0, return this.tarefas.length === 0.

[07:54] Então nossa propriedade computed vai retornar o booleano, verdadeiro ou falso, que indica se a lista está vazia ou não.

[08:04] E se a lista está vazia, ou seja, se vai me retornar true eu quero exibir o box. Senão, eu não quero exibir o box e quero deixar só a lista de tarefas. Então no nosso box vamos usar nossa diretiva v-if, <Box v-if="listaEstaVazia">. Se a lista está vazia eu quero exibir a minha mensagem dizendo que o usuário não está muito produtivo hoje. Vou salvar.

[08:38] Vou recarregar a página no navegador, a lista está vazia e ele exibiu a mensagem. Vou colocar uma nova tarefa “Estudar TS”, iniciar e finalizar. E agora sim, repara que ele não exibe mais o box com aquele placeholder, com aquele conteúdo padrão dizendo que o usuário não está produtivo.

[09:00] É exatamente isso que queríamos. Agora estamos conseguindo controlar e exibir uma mensagem amigável para o usuário, para quando ele ainda não adicionou nenhuma tarefa na lista.

@@07
Faça como eu fiz

Praticar ajuda bastante no aprendizado de um novo conceito. Assim, é muito importante que você implemente o que foi apresentado nesta aula.

Não deixe de sanar suas dúvidas antes de dar continuidade ao curso. Estaremos te esperando no fórum da Alura caso alguma dúvida surja.

@@08
O que aprendemos?

Nessa aula, você aprendeu:
Renderizar listas com o v-for;
Utilizamos um mecanismo de repetição para renderizar N vezes uma tarefa, onde N é o tamanho da lista. Isso faz com que nossa lista seja dinâmica.
Condicionais com v-if / v-else;
Aprendemos como esconder ou exibir um componente, dado um estado específico utilizando a diretiva v-if.
Fallback de conteúdo com o operador || (OU);
Utilizamos o operador OU para exibir um texto padrão, caso a tarefa não possua uma descrição.
Slots.
Aprendemos a lidar com o slot quando criamos um componente para representar o Box. Assim, conseguimos exibir os elementos filhos dentro do nosso Box.

#### 05/02/2024

@04-Estilos estilosos

@@01
Projeto da aula anterior

Caso queira começar daqui, você pode baixar o projeto da aula anterior nesse link.

https://github.com/alura-cursos/alura-tracker/tree/aula-3

@@02
Preparando o modo escuro

[00:00] No nosso Alura Tracker já conseguimos iniciar e finalizar tarefas e popular a nossa lista de tarefas executadas, tudo do jeito que precisávamos.
[00:09] E agora vamos partir para uma funcionalidade mais visual. Queremos adicionar a opção de um modo escuro. O usuário poderá ativar e desativar esse modo escuro. E vamos alterar tanto o fundo quanto a cor primária.

[00:27] Tem várias formas diferentes de fazer isso, e no Alura Tracker vamos usar variáveis CSS. Então vamos entrar no nosso “App.vue”.

[00:44] O que eu quero é adicionar essas variáveis. A partir da nossa tag principal, que é a main, vamos criar algumas variáveis. Vamos chamar a primeira variável de bg-primario, que será o nosso backgroud primário, que no nosso caso é branco: --bg-primario: #fff;.

[01:05] Depois vamos para o texto primário, que será preto: --texto-primario: #000;. E agora queremos trocar as cores quando o modo escuro estiver ativo. Então como vamos utilizar o CSS para fazer isso?

[01:27] Quando existe uma classe modo escuro, main.modo-escuro, nós vamos alterar o valor dessas variáveis. Para o bg-primario vou pegar o hexadecimal da minha cola, que vai ser um azul bem escuro, --bg-primario: #2b2d42;. E a cor do texto será mais clara. --texto-primario: #ddd;.

[01:49] Então vamos começar a colocar isso para funcionar. Primeiro vamos ativar o modo escuro por padrão, <main class="columns is-gapless is-multiline modo-escuro">.

[02:01] Agora vamos pegar a parte da direita que está branca, vamos adicionar uma classe chamada “conteúdo”, que é o conteúdo da nossa aplicação e vamos utilizar essa variável.

[02:14] Então nosso .conteúdo terá um background color, que é justamente essa variável que acabamos de criar, background-color: var(--bg-primario);. Vamos salvar e ver se isso funciona no navegador.

[02:31] Já está um azul bem escuro. E agora precisamos tratar a parte do formulário. Vamos entrar no “Formulario.vue” e adicionar as cores disponíveis. Vamos colocar uma classe para representar nosso formulário.

[02:58] Vamos adicionar nosso <style>. Dessa vez não queremos que ele seja escopado, queremos que ele passe para todos os componentes filhos. E queremos que todo mundo dentro do .formulario tenha uma cor de fonte da variável texto-primario, color: var(--texto-primario);.

[03:26] Vamos ver se isso vai funcionar. Faltou mudar a cor de fundo também. Então nosso background do .formulario vai ser a variável bg-primario, background -color: var(--bg-primario);.

[03:45] Vamos verificar no navegador. Agora funcionou. Está faltando ainda no nosso cronômetro. Então vamos adicionar no cronômetro essa cor de variável. No “Cronometro.vue” vamos adicionar nosso <style scoped>. E na nossa seção vamos adicionar uma classe="display" que será o display do nosso cronômetro.

[04:10] E vamos também seguir utilizando as variáveis no estilo de .display. A cor da fonte será color: var(--texto-primario);.

[04:26] Vamos salvar. Agora sim, tudo funcionando conforme o esperado. Quando o modo escuro está ativo nós vemos uma cor de fonte mais clara. E quando o modo está inativo ele volta ao normal.

[04:50] Já temos os dois modos bem definidos. E o que precisamos agora é adicionar uma funcionalidade para o usuário conseguir fazer essa alteração.

[04:59] Então vamos adicionar um botão na barra lateral que, conforme o usuário clica e interage, ele vai conseguir ativar ou desativar esse modo escuro.

@@03
Para saber mais: Variáveis CSS

O uso de variáveis CSS é poderoso, não deixe de conferir aqui.

https://cursos.alura.com.br/course/mobile-first-layouts-responsivos/task/75492

@@04
Ouvindo a troca de tema

[00:00] Nosso modo escuro já está funcionando. E agora vamos partir para adicionar uma opção para o usuário poder escolher qual dos modos ele quer que fique ativo.
[00:10] Vamos entrar na nossa “BarraLateral.vue”. Logo abaixo do h1 vamos adicionar um botão e utilizar a classe do Bulma para ficar um botão bem estilizado, <button> class="button". Vamos chamá-lo de Ativar modo escuro. Ele já apareceu no navegador.

[00:35] Vamos centralizar esse texto todo, então no header vamos adicionar uma propriedade nova, com text-align: center;. Agora ele centralizou nossa imagem e o botão de ativar o modo escuro.

[00:49] Agora, dado o clique desse usuário temos que avisar que o estilo está sendo trocado, que ele está alterando o modo que ele quer ativo.

[01:01] Então quando o usuário clicar, queremos alterar o modo. Então @click=”alterarTema”. Agora vamos criar esse método: methods: { alterarTema ( ) { } }.

[01:28] Nós não vamos controlar esse tema nessa parte. Nós vamos controlar o tema no “App.vue”. E já aprendemos como fazer um componente filho se comunicar com o pai, que é através da emissão de eventos. Então teremos nossa propriedade emits, que vai receber um array de strings com todos os eventos que ele emite. Vamos chamar de emits: [‘aoTemaAlterado’].

[02:02] E quando o usuário clicar vamos fazer essa emissão, lembrando que o primeiro parâmetro é o nome do evento: this.$emit(‘aoTemaAlterado’). E no nosso caso só temos dois modos: só poderemos ativar e desativar o modo escuro.

[02:27] Então vamos criar o estado local, que também já vimos como fazer, usando o método data (), que retorna um objeto, que será o modoEscuroAtivo, que por padrão será false.

[02:45] Então toda vez que o usuário trocar, vamos alterar o valor desse booleano. Então toda vez que ele clicar vamos pegar o modo escuro e substituir pelo oposto. Se for false vai ficar true e vice-versa. E com isso vamos conseguir inclusive passar isso adiante. methods: { alterarTema ( ) { this.modoEscuroAtivo = !this.modoEscuroAtivo this.$emit('aoTemaAlterado', this.modoEscuroAtivo)} }.

[03:09] Agora, quando esse modo estiver ativo, temos que trocar o texto do botão. Então vamos criar nossa propriedade computada para deixar isso certo para o usuário: computed: { textoBotao ( ) { } }.

[03:32] E vamos dizer que se o modo escuro está ativo nós vamos retornar “Desativar modo escuro”. Caso contrário, vamos retornar “Ativar modo escuro”. if (this.modoEscuroAtivo) { return 'Desativar modo escuro' } return 'Ativer modo escuro'}.

[03:54] Se o modo escuro está ativo, o texto é desativar. Senão, o texto é ativar. Agora já podemos usar essa variável textoBotao dentro do <button> para ficar com o texto do botão correto.

[04:06] Vamos ver se esse monte de códigos vai funcionar. Voltando para o navegador, ativar e desativar modo escuro, botão já está funcionando como deveria. E agora precisamos ouvir isso no nosso “App.vue”. Então na barra lateral vamos escutar o evento @aoTemaAlterado, e nós vamos trocar o tema.

[04:35] Agora vamos criar esse método trocarTema(). Ele vai receber um booleano por padrão, que é o modoEscuroAtivo.

[04:54] Agora precisamos adicionar, quando o modo escuro estiver ativo queremos fazer alguma coisa. Se não estiver, não queremos adicionar essa classe.

[05:05] Para isso, a primeira coisa que faremos é trazer esse estado. O estado vai controlar o texto do botão, e abaixo o estado vai controlar o modo, se ele está ativo ou inativo. Então modoEscuroAtivo: false.

[05:29] E quando o usuário trocar vamos fazer a troca. O que recebermos por padrão vamos colocar no nosso estado. Essa propriedade que estamos recebendo por parâmetro é um booleano. Dado o que estamos recebendo, vamos alterar o nosso estado, trocarTema (modoEscuroAtivo: boolean) { this.modoEscuroAtivo = modoEscuroAtivo.

[06:02] Agora, caso o modo escuro esteja ativo, temos que adicionar uma classe. Caso contrário, não. Para fazer isso usando o Vue, vamos adicionar outra propriedade classe na tag main, agora usando dois pontos na frente, :class="{}". Ou seja, vai código JavaScript.

[06:30] E essa propriedade vai receber um objeto. Qual é o nosso objetivo caso o modo escuro esteja ativo? A classe vai existir ou não baseado no nosso estado.

[06:48] Na nossa esquerda, o nome da nossa propriedade é a classe que queremos adicionar, então :class=”{ ‘modo-escuro’ }”.

[06:56] E na direita vamos passar um booleano, ou seja, vamos passar uma flag de falso ou verdadeiro: :class=”{ ‘modo-escuro’ : modoEscuroAtivo}. E o que o Vue vai fazer por baixo dos panos? Se o modo escuro estiver ativo, ele vai adicionar essa classe. Se não estiver ativo, ele não adiciona. Vamos salvar e testar se o modo escuro está finalmente funcionando no navegador.

[07:23] Se clicarmos fica escuro e se clicarmos de novo ele remove o modo escuro. Agora sim já temos a funcionalidade completa de fazer a troca desse modo escuro. Podemos ativar ou desativar de acordo com a nossa vontade.

@@05
Estilos e objetos

[00:00] Agora, além de fazer o tracking das tarefas diárias do nosso usuário, já temos também o modo escuro, podemos alterar e dizer o que queremos ou não.
[00:17] Antes de seguirmos para a parte final do nosso curso, que é onde tentaremos publicar a nossa aplicação, vale a pena conferir um outro jeito de aplicar estilo.

[00:29] Vamos dar uma revisada no código da barra lateral, por exemplo. Temos aplicado vários estilos no nosso CSS, às vezes escopado, às vezes não. Nosso arquivo "Box.vue", por exemplo, tem um background color.

[00:45] E esse não é o único jeito que o Vue nos permite aplicar nosso estilo, nosso CSS. Podemos fazer, por exemplo, um bind direto com as nossas propriedades utilizando a propriedade style.

[01:03] Podemos passar um objeto que fará toda a configuração dos estilos para esse componente, :style="estilos". Então vamos criar esse “estilos” aqui no nosso "Box.vue". Vamos usar o data (), que é o estado, retornando um objeto, passando o nosso estilo, return { estilos:. E finalmente podemos trazer o que queremos configurar para o nosso box.

[01:30] Então podemos pegar esse estilo CSS que estamos passando aqui, background, e jogar para dentro de estilos, vamos tirar totalmente esse trecho de código do <style scoped> daqui. Vamos testar para ver se isso continua funcionando. Vamos atualizar a página do Alura Tracker.

[01:49] Repare que nosso box continua do jeito que ele funcionava antes, já com a cor direto fazendo o bind com a propriedade.

[01:58] Isso pode facilitar nossa vida se são propriedades que mudam determinado estado do componente. Por exemplo, podemos ter um alerta vermelho para uma mensagem de erro ou verde para uma mensagem de sucesso. E usando dessa forma conseguimos controlar via JavaScript o que estamos passando.

[02:22] E vale ressaltar que como passamos o background não houve problema nenhum. Mas se quiséssemos passar a propriedade background-color, poderíamos fazer de duas formas: podemos passar entre aspas, 'background-color': '#FAF0CA' , que ele vai continuar funcionando como deveria.

[02:44] Ou então podemos usar o CamelCase e ao invés de passar com hífen vamos passar com o C maiúsculo, e ele vai entender que isso quer dizer que tem um hífen separando as palavras, backgroundColor: '#FAF0CA'.

[03:02] Isso funciona para todos os estilos CSS. Então além de programar nosso CSS na propriedade style, também podemos fazer isso diretamente via JavaScript, linkando as propriedades de um objeto com as propriedades CSS que ele precisa ter.

[03:18] Simples assim, é uma nova forma de trabalhar com o CSS que você pode utilizar nos seus projetos do dia a dia.

@@06
Programação em par

Cláudia implementou a troca de modos, entre o claro e o escuro. Mas, por algum motivo, o tema está invertido. Quando deveria estar escuro, está claro e vice-versa.
O código que ela escreveu é o seguinte:

<template>
  <header>
    <h1>alura <strong>tracker</strong></h1>
    <div class="has-text-centered">
      <button class="button" @click="alterarModo">Ativar modo {{ textoBtn }}</button>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BarraLateral",
  emits: ['aoAlterarModo'],
  data () {
    return {
      modoEscuro: false
    }
  },
  methods: {
    alterarModo () : void {
      this.$emit('aoAlterarModo', this.modoEscuro)
      this.modoEscuro = !this.modoEscuro
    }
  },
  computed: {
    textoBtn () : string {
      return this.modoEscuro ? 'claro' : 'escuro'
    }
  }
});
</script>COPIAR CÓDIGO
Selecione uma alternativa

O bug existe porque Cláudia está alterando o valor do estado modoEscuro depois de emitir o evento. Logo, o valor propagado está invertido.
 
Alternativa correta! Exatamente! Programação em par (ou pair programming) ajuda muito quando ficamos presos muito tempo numa mesma lógica. Chamar alguém com a cabeça fresca é uma excelente alternativa. Aqui na Alura você pode usar o nosso fórum sempre que precisar!
Alternativa correta
Basta iniciar o modo escuro como true.
 
Alternativa correta
Cláudia pode negar a condição this.modoEscuro no textoBtn.

@@07
Faça como eu fiz

Praticar ajuda bastante no aprendizado de um novo conceito. Assim, é muito importante que você implemente o que foi apresentado nesta aula.

Não deixe de sanar suas dúvidas antes de dar continuidade ao curso. Estaremos te esperando no fórum da Alura caso alguma dúvida surja.

@@08
O que aprendemos?

Nessa aula, você aprendeu:
Uso de variáveis CSS para temas (claro/escuro);
Utilizando essas variáveis, nós podemos facilmente controlar o tema do nosso Alura Tracker, alterando a cor de fundo e a cor do texto de acordo com o tema aplicado.
Adicionar e remover classes baseado num estado do componente;
Aprendemos a adicionar ou remover classes, condicionalmente utilizando a diretiva :class.
Estilos via objetos.
Aprendemos uma nova forma de aplicar estilos a um elemento, utilizando um objeto que representa as propriedades e seus valores.