---
layout: post
title:  "Aprendendo o básico de React"
tags:
  - javascript
  - react
  - api
  - framework
hero: https://source.unsplash.com/collection/1129594/
overlay: green
published: true
---

# Curso ReactJS

Olá pessoal, meu nome é [**Diogo Cezar**](mailto:diogo@diogocezar.com), e é com muita felicidade que estou compilando neste material, um pouquinho do que aprendi _por enquanto_ sobre a tecnologia ReactJS.

Gostaria de dar os devidos créditos a uma boa parte deste material que foi inspirado no curso _starter_ ReactJS da RocketSeat. Este material original pode ser acessado aqui: https://rocketseat.com.br/

## Pré-requisitos

O ReactJS é uma tecnologia que envolve uma série de prévios conhecimentos. Você até pode começar a jornada de dev Front-End por um destes frameworks modernos (como o ReactJS), mas certamente irá sentir alguma dificuldade em entender como as coisas realmente funcionam. Por isso eu recomendo que, se você é extramamente iniciante, siga o seguinte **RoadMap**:

1. Como a internet funciona;
2. O Protocolo HTTP;
3. HTML5;
4. CSS3;
5. JavaScript Vanilla (Para navegadores);
6. JavaScript Moderno (ES6+);
7. Babel;
8. Webpack;
9. Gerenciadores de Pacotes;

A seguir um link para uma série de materiais que podem te ajudar nesta jornada e nivelamento.

[Exemplos Básicos](https://github.com/diogocezar/dctb-utfpr#programa%C3%A7%C3%A3o-web-1)

Você também pode dar uma olhada em alguns exemplos compilados neste link:

[Exemplos JavaScript](https://github.com/diogocezar/dctb-utfpr-2019-1-web/tree/master/a08-javascript)

## Organização do Minicurso

Vou dividir este minicurso sobre ReactJS em **5 módulos**.

Segue o índice para cada um dos módulos:

- [Módulo 1 - Introdução](#módulo-1---introdução)
- [Módulo 2 - Estados](#módulo-2---estados)
- [Módulo 3 - Aplicação GitHub](#módulo-3---aplicação-github)
- [Módulo 4 - Capturando dados de uma Api](#módulo-4---capturando-dados-de-uma-api)
- [Módulo 5 - Eventos](#módulo-5---eventos)
- [Módulo 6 - Propriedades](#módulo-6---propriedades)
- [Módulo 7 - Passando Funções por Propriedades](#módulo-7---passando-funções-por-propriedades)
- [Módulo 8 - Rotas](#módulo-8---rotas)
- [Módulo 9 - Styled Components](#módulo-9---styled-components)
- [Módulo 10 - Hooks](#módulo-10---hooks)
- [Módulo 11 - Redux](#módulo-11---redux)

## Módulo 1 - Introdução

### O que é ReactJS?

- Aplicações web são divididas em 2 pates: **Front-End** e **Back-End**;
- **Back-End**: Lado do Servidor; (PHP, Ruby, NodeJS, Python);
- **Front-End**: É a parte visual (HTML + CSS + JS);
- **ReactJS** Atua no **Front-End**;
- Qual problema ele resolve?
  - Faz mais que o JS puro consegue fazer;
  - **Organiza** o nosso projeto;
  - Manipula a DOM;
  - Utilizado para construção de **SPA's**;

#### O que são SPA's?

Tradicionalmente, em uma aplicação _web_ renderizada pelo servidor, nós possivelmente teríamos um modelo **MVC**, e cada **View** deste modelo seria responsável por criar uma tela, chamada por uma rota. Um exemplo clássico de uma aplicação web.

Uma **SPA** é uma forma diferente de trabalhar com uma aplicação.

Com essa tecnologia, têm-se apenas **uma página principal** e todas as outras serão escritas e modificadas pela linguagem de programação **JavaScript**.

De acordo com essa abordagem: O **Back-End** ao invés de retornar o próprio HTML formatado, retorna os dados no formato **JSON**. Essas são as nossas famosas **API's**.

E desta forma, o **Back-End** fica totalmente separado do **Front-End**.

Isso permite bastante flexibilidade, inclusive na parte interativa (animações, efeitos, etc...)

### Hello World

Podemos ver aqui https://reactjs.org/

Um simples exemplo em ReactJS, que mostra mais ou menos isso:

```js
class HelloMessage extends React.Component {
  render() {
    return <div>Hello {this.props.name}</div>;
  }
}

ReactDOM.render(
  <HelloMessage name="Taylor" />,
  document.getElementById("hello-example")
);
```

A princípio este é um código JavaScript que utiliza apenas imprime na tela: **Hello Taylor**, um tanto quanto complexo para fazer só isso né? Mas vamos entender que o que estamos fazendo aqui vai ajudar, e muito, nossas aplicações web.

A palavra chave é **COMPONENTE**!

Note que temos uma notação um tanto quanto "estranha"! Uma função que retorna um HTML? Isso é possível?

**SIM!** E isso é o grande lance do ReactJS, permitir a "escrita" de algo que se parece muito com HTML dentro de um código JavaScript.

Para isso, o ReactJS utiliza uma tecnologia chamada JSX, então o que vemos na tela não é HTML propriamente dito, e sim, um código JS que vai ser transformado em HTML puro.

Mas vamos entender tudo isso ao longo das próximas explicações.

Para nos familiarizarmos com o ReactJS, vamos primeiro configurar o ambiente e preparar um exemplo básico para sua utilização.

### Configurando o Ambiente

Para criar um projeto em **ReactJS** temos que preencher alguns "pré-requisitos".

O primeiro deles é ter o **NodeJS** e o **NPM** instalados em sua máquina. Para isso, basta seguir as instruções em: https://nodejs.org/

Também iremos utilizar o **yarn** um gerenciador de pacotes, para isso: https://yarnpkg.com/

#### Verificando se tudo está ok!

Podemos executar os seguintes comandos em um terminal, esperando receber as versões das ferramentas instaladas.

```bash
node -v
npm -v
yarn -v
```

Agora, estamos prontos para criar nossa primeira aplicação.

### Instalando o create-react-app

Agora, precisamos instalar uma ferramenta "mágica" que irá fazer todo o trabalho "chato" de configuração do **Babel** e do **Webpack** que são ferramentas que permitem a utilização de JavaScript moderno nos nossos navegadores.

Para isso, vamos instalar essa ferramenta de forma global em nossa máquina.

```bash
npm install -g create-react-app
```

Com ela instalada, passamos para a criação do projeto.

### Criando nosso primeiro projeto

Agora podemos criar um novo projeto utilizando o comando:

```bash
create-react-app gitapp
```

**gitapp** é o nome da aplicação de exemplo que nós iremos utilizar durante todo o curso. Mas você poderia escolher qualquer nome aqui.

Esse passo deve demorar um pouco até a instalação completa de todos os pacotes.

Quando tudo estiver terminado, Agora podemos entrar em nossa pasta e analisar os arquivos que foram criados.

### Estrutura de Pastas

Vamos agora, dentro da pasta que foi criada, analisar cada um dos diretórios e arquivos previamente criados:

**node_modules** é onde ficarão as dependências dos nossos projetos;

**public** são todos os arquivos que vão ser acessíveis pelo usuário final da nossa aplicação;

**src** é a pasta onde ficará todo o código da nossa aplicação;

**.gitignore** é um arquivo de configuração do git, para ignorar o node_modules, por exemplo.

**package.json** é o arquivo de configuração do nosso projeto web, também é neste arquivo que estarão listadas as dependências do nosso projeto.

Notemos que inicialmente ele já instalar algumas dependências:

- **react** é o react em sí;
- **react-dom** é o que faz as interações com o html;
- **react-script** são os scripts para automatizar a transpilação de códigos;

em **scripts**, temos os scripts que podemos utilizar para começar a aplicação (start) por exemplo, ou até mesmo criar a versão final (build).

o **README.md** é a documentação do projeto.

o **yarn.lock** é o "cache" das versões dos pacotes já baixados.

Agora podemos enfim rodar a nossa aplicação, utilizando o comando:

```bash
yarn run start
```

Se tudo deu certo, deve aparecer em sua tela o logo do ReactJS.

### O que são componentes?

Para entender melhor o que são os nossos **componentes** vamos alterar um pouco a estrutura do nosso projeto inicial, para isso, remova os arquivos:

- ~~src/App.css~~
- ~~src/App.test.js~~
- ~~src/index.css~~
- ~~src/logo.svg~~
- ~~src/serviceWorker.js~~

Agora, é necessário remover as chamadas dos arquivos removidos em App.js e index.js

Ficamos então com:

**index.js**

```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));
```

**App.js**

```js
import React from "react";

const App = () => {
  return <h1>Olá ReactJS</h1>;
};

export default App;
```

Agora podemos salvar, e analisar o nosso projeto. Vejamos que ele já alterou as informações.

Agora sim, podemos trabalhar com o conceito de componentização.

SEMPRE o arquivo **index.js** vai ser o primeiro arquivo a ser aberto pelo ReactJS.

A partir dele é que todos os outros arquivos serão chamados.

Note que temos alguns imports:

```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
```

Basicamente, todas as vezes em que for necessário utilizar JSX (HTML+JS) vamos precisar importar o **React**.

Neste caso o **ReactDOM** será o responsável por "linkar" nossa aplicação ao nosso arquivo html principal (index.html)

E o import do **App** é a importação do nosso único componente!

```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));
```

Note ainda, que estamos renderizando o nosso primeiro "componente" (App) dentro da div "root" no nosso arquivo **index.html**

Agora, vamos analisar melhor o **index.html**

Abra o arquivo e veja que a div root existe dentro dele. Ou seja, todos os nossos elementos "HTML" serão criados "virtualmente" dentro desta única div principal chamada root.

Voltemos para o ReactJS, e aqui... TUDO é componente!

Botões, links, imagens, inputs, e até mesmo páginas completas!

Por isso, o nosso **App** é um "componente" que representa toda a nossa página inicial!

Um componente poderia ser definido por:

> Um conjunto de parte visual (que é o nosso HTML) a parte funcional (que é JavaScript) e a parte de estilização (que é o CSS)

Então um componente é um elemento _completo_ e _auto-contido_ que encapsula essas três funcionalidades e uma única responsabilidade.

Podemos entender agora que cada pequena parte da nossa aplicação é um _componente_.

Sabendo que um componente pode ser formado por outros componentes, podemos levar isso a vários sub-níveis para formar componentes mais complexos, a partir de componentes mais simples.

**Atividade**: Acesse uma página qualquer da Internet, e tente identificar mentalmente quais dos elementos que você vê, poderiam ser componentes. Lembre-se, eles tudo pode ser um componente, e um componente também pode ser formado por outros componentes.

### Tipos de Componentes

Em **ReactJS** nós temos 2 principais tipos de componentes: **Componentes com Estados** e **Componentes sem Estados**

Também são conhecidos por (_StateLess_ e _StateFull_);

Os dois componentes tem as mesmas características, já citadas anteriomente, com a diferença que: um componente **com estados** possui **atributos** que poderão ter o seu valor alterado, e a cada alteração, impactarão diretamente na renderização do componente.

Analogamente, poderíamos pensar em uma Classe da orientação a objetos. Imagine que uma classe tem uma série de atributos. Imagine ainda que, o ReactJS vai pedir para "REIMPRIMIR" toda essa classe, todas as vezes em que você alterar qualquer uma dessas propriedades.

Já, os componentes sem estados, são componentes mais simples, que quase sempre só servem para renderizar uma responsabilidade pequena de nossa página.

Outra diferença muito importante é a **forma** como estes componentes são escritos.

Um componente com estados quase sempre vai ser representado, de fato, por uma classe, por exemplo:

```js
import React, { Component } from "react";

class App extends Component {
  render() {
    return <h1>Olá ReactJS</h1>;
  }
}

export default App;
```

Note que para este componente nós temos obrigatoriamente que utilizar o método `render()` pois ele será o responsável por colocar e recolocar as informações na tela.

Mas, EXATAMENTE o mesmo componente, poderia ser escrito da seguinte forma:

```js
import React from "react";

const App = () => {
  return <h1>Olá ReactJS</h1>;
};

export default App;
```

Com a diferença que neste segundo caso, não seria possível utilizar os estados dentro do componente. A não ser que utilizássemos os Hooks, que podem ser visto mais detalhadamente: https://willianjusten.com.br/habemus-react-hooks/ ou no capítulo [Módulo 10 - Hooks](#módulo-10---hooks)

## Módulo 2 - Estados

Os estados, correspondem as modificações de um componente, e aqui é uma grande dificuldade, mudar o _MindSet_ de quem já programa ou desenvolve em JavaScript pode ser inicialmente trabalhoso.

Vamos pensar o seguinte, se nós estivéssemos trabalhando com _JS Vanilla_ ou _JQuery_, nós precisaríamos, depois de executar algum processo, atribuir este resultado em uma div do nosso HTML, correto? Algo como:

```js
const soma = (a, b) => a + b;
document.querySelector("#root").innerHTML = `Soma é: ${(3, 4)}`;
```

Isso seria bem comum...

Mas o **ReactJS** utilizar justamente este nome por ser **reativo**.

Isso implica que, como já falamos, nosso componente vai ter atributos, e toda vez que um atributo for alterado, ele vai pedir para renderizar o componente novamente!

Em um exemplo bem simples, poderíamos ter algo do tipo:

```js
import React, { Component } from "react";

class App extends Component {
  state = {
    result: 0
  };
  soma = (a, b) => {
    this.setState({ result: a + b });
  };
  render() {
    return <h1>Soma é {this.state.result}</h1>;
  }
}

export default App;
```

Obviamente, este é um exemplo que não faz nada, pois a função soma nunca é chamada, mas dá para entender/mostrar que... todas as vezes em que ela for chamada, automaticamente o atributo `result` será alterado, e consequentemente o método `render()` será chamado novamente.

Para entender um exemplo _completinho_, vamos pensar em um componente que seria um Relógio:

```js
import React, { Component } from "react";

class Clock extends Component {
  state = {
    now: null
  };

  componentDidMount() {
    setInterval(() => {
      this.setState({ now: new Date().toLocaleTimeString() });
    }, 1000);
  }

  render() {
    return <h1 className="clock">{this.state.now}</h1>;
  }
}

export default Clock;
```

Note que para que nós possamos utilizar o estado, tivemos que utilizar uma classe!

Mas neste código, temos muitas coisas novas!

Vamos entender cada um dos seus novos conceitos!

1. Note que agora estamos utilizando uma nova sintaxe dentro do método render: `<h1>{this.state.now}</h1>` isso significa o próprio JSX, ou seja, uma mistura entre HTML e JavaScript.
   Neste caso, nós estamos pedindo para que dentdo de uma tag `<h1>` nós coloquemos o conteúdo da variável `this.state.now`. `this` é referente a própria classe, `state` é o controle de estados deste componente, onde todos os estados vão ficar e `now` é o nome da nossa variável;

2. No início da classe temos algo como: `state = { now: null };`. Aqui estamos representando a declaração do nosso atributo de estado, inicialmente valendo `null`.

3. Notemos tambem um novo método sendo chamado dentro da classe: `componentDidMount` este método faz parte do ciclo de vida dos componentes com estado do ReactJS. Isso significa que, componentes com estado vão possuir alguns métodos especial que podem interceptar alguns momento de seu ciclo de vida, neste caso estamos utilizando um método que vai executar uma função no momento em que o componente for montado, ou seja, quando ele estiver pronto para ser exibido em tela. Neste caso, estamos utilizando uma função que irá setar um intervalo de tempo para executar uma função que irá alterar o estado do nosso componente a cada 1 segundo.

4. A forma de alterar um estado. O ReactJS aplica um importante conceito de imutabilidade, isso significa que por definição, não poderíamos, por exemplo, fazer o seguinte: `this.state.now = 'xyz'` pois isso vai de encontro com o princípio da imutabilidade, no qual, nenhum estado deve ser diretamente alterado. Por isso, devemos utilizar um método especial chamado `setState()` que recebe como parâmetro como será o novo estado do componente;

5. E por último, de onde vem a mágica? Como o react muda o valor da variável, toda vez que o estado é alterado? A resposta é simples! Por definição, sempre que um estado de um componente é alterado, o react chama novamente o método de `render()` por isso, não precisamos nos preocupar em renderizar isso novamente no DOM, pois o próprio ReactJS faz este trabalho para nós!

## Módulo 3 - Aplicação GitHub

Agora que temos em mente os principais conceitos sobre os componentes, podemos dar início a um projeto que servirá de exemplo para fixar os principais conceitos sobre ReactJS.

Este projeto será um **Front-End** simples para nós listarmos os repositórios de algum usuário do GitHub.

Mas vamos passo a passo, entendendo suas principais funcionalidades.

### Criando o Header

Vamos criar o primeiro componente que será o header da nossa aplicação. Também vamos fazer uma estilização básica para este cabeçalho.

Vamos então começar a organizar nossos componentes. Em `/src` vamos criar uma nova pasta chamada `components`

Cada componente deve ser colocado em uma pasta, isso é uma **boa prática**, pois dentro desta pasta nós colocaremos o próprio componente sempre chamado de `index.js`, e um arquivo chamado `styles.css` que serão as estilizações daquele componente.

Então criaremos os seguintes arquivos:

1. `src/components/Header/index.js`
2. `src/components/Header/styles.css`

Também, vamos refatorar um pouco nossa estrutura anterior!

É comum colocar nossas páginas em pastas separadas, por isso vamos mover o `src/App.js` para `src/pages/Main.js` e também criar um estilo para ela `src/pages/styles.css`

E aproveitando, vamos também criar uma pasta para o nosso componente Clock: `src/components/Clock/index.js` e também um estilo para ele `src/components/Clock/styles.css`.

Neste momento, nossa estrutura de pastas deve ficar parecida com:

```
src
|-- components
|   |-- Clock
|   |   |-- index.js
|   |   `-- styles.css
|   `-- Header
|       |-- index.js
|       `-- styles.css
|-- index.js
`-- pages
    `-- Main
        |-- index.js
        `-- styles.css
```

Claro, que agora precisamos ajustar os nosso componentes, então seguem as modificações de cada um dos arquivos:

**src/index.js**

```js
import React from "react";
import ReactDOM from "react-dom";
import Main from "./pages/Main"; // nova importação da página Main
ReactDOM.render(<Main />, document.getElementById("root"));
```

**src/pages/Main/index.js**

```js
import React, { Fragment } from "react"; // Novo elemento importado { Fragment }
import Header from "../../components/Header"; // Importação do Header
import Clock from "../../components/Clock"; // Importação do Clock
const Main = () => {
  return (
    <Fragment>
      <Header />
      <Clock />
    </Fragment>
  );
};
export default Main;
```

Estamos aqui aprendendo a **importar** nossos primeiros componentes! Isso significa que dentro deste contexto, nós teremos os componentes **Header** e **Clock** para serem utilizados "como" tags HTML. Então, no lugar em que forem inseridas essas tags,será exibido o conteúdo do seu respectivo componente.

Outro detalhe importante é em relação a um novo componente chamado **Fragment** importado diretamente de "react".

Isso acontece pois, por definição, o react só consegue renderizar uma única tag por componente, e neste caso queremos utilizar 2: Header e Clock! Uma solução mais "antiga" seria colocar ambos os componentes em uma `<div>` vazia. O problema disso é que nós "sujamos" o código com div's. O **Fragment** é uma alternativa mais moderna para resolver este problema, pois encapula vários componentes sem a necessidade de adicionar uma nova div ao código fonte.

Agora vamos analisar o componente Header:

**src/components/Header/index.js**

```js
import React from "react";
import "./styles.css";

const Header = () => <header id="main-header">Git App</header>;

export default Header;
```

Note que aqui estamos importando o arquivo **styles.css** que irá adicionar uma melhor aparência ao nosso header.

**src/components/Header/styles.css**

```css
header#main-header {
  width: 100%;
  height: 60px;
  background: #da552f;
  font-size: 1.2rem;
  font-weight: bold;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Neste momento já podemos rodar a aplicação e analisar o resultado até este ponto.

O resultado esperado é o header, e o relógio sendo executados!

Vamos agora aplicar um estilo global, para melhorar um pouco a aparência geral dos elementos. Isso pode ser feito de várias formas, mas neste caso vamos apenas criar um novo arquivo CSS, e incluí-lo no projeto principal.

**/src/styles.css**

```css
* {
  margin: 0;
  padding: 0;
  outline: 0;
  box-sizing: border-box;
}

:root {
  font-size: 14px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  background: #fafafa;
  color: #333;
}
```

**src/pages/Main/index.js**

```js
import React, { Fragment } from "react";
import Header from "../../components/Header";
import Clock from "../../components/Clock";
import "./styles.css"; // Estilos globais adicionados
const Main = () => {
  return (
    <Fragment>
      <Header />
      <Clock />
    </Fragment>
  );
};
export default Main;
```

E para finalizar essa parte, vamos também colocar um estilo para o Clock:

**src/components/Clock/styles.css**

```css
h1.clock {
  width: 100%;
  height: 60px;
  font-size: 4rem;
  font-weight: bold;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
  margin-top: 10px;
}
```

Da mesma forma este css deve ser importado dentro do componente Clock.

**src/components/Clock/index.js**

```js
import React, { Component } from "react";
import "./styles.css";
class Clock extends Component {
...
```

Até aqui entendemos como funcionam os componentes, e temos os conhecimentos básicos para começar a manipular os estados dos componentes.

Na sequência, iremos obter os dados de um repositório no GitHub, popular o estado de um componente e mostrar estes dados em tela.

## Módulo 4 - Capturando Dados de uma API

### Capturando os Dados de uma API

A primeira coisa a ser feita, é a instalação de uma nova biblioteca no nosso projeto, para isso, basta executar o comando:

```bash
yarn add axios
```

O Axios é uma ferramenta que facilita a chamada de uma requisição assíncrona, ele é bem consolidado entre a comunidade. Mas neste ponto, você também poderia utilizar outras alternativas para isso, o próprio comando `fetch`.

> Lembrando que aqui, vamos precisar dos entendimentos de como funciona uma promise, se vc não entende muito bem como elas funcionam na linguagem JavaScript, vale a pena fazer uma pausar, e dar uma estudada nisso.

A partir deste momento, temos a opção de fazer um **import** desta biblioteca em qualquer um dos nossos componentes. Para isso, basta incluir o comando:

```js
import axios from "axios";
```

Uma boa prática, é criar um arquivo específico para a realização das chamadas da api, para isso, vamos criar na raiz do nosso projeto uma nova pasta chamada **services** e dentro dela, um arquivo chamado **api.js**.

Como dito, neste exemplo, vamos buscar os repositórios de um usuário no GitHub!

Para isso vamos utilizar a seguinte url:

https://api.github.com/users/diogocezar/repos

Note que, basta alterar `diogocezar` por outro usuário para obter os seus repositórios!

> Você pode testar essa URL em seu navegador, por exemplo e analisar os resultados.

Nosso arquivo **api.js**, deve preparar uma função para obter os dados desta api, ficando desta forma:

**services/api.js**

```js
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.github.com/users/diogocezar/repos"
});

export default api;
```

Aqui estamos utilizando a criação de uma instância do axios, para preparar a api para sempre retornar os dados com base nessa url (baseURL).

Agora vamos criar uma novo componente. A princípio, ele deve listar os dados desta api. Criamos então um componente: `src/components/List/index.js`, e nele, vamos importar o serviço que acabamos de criar:

**src/components/List/index.js**

```js
import React, { Component } from "react";
import api from "../../services/api";
import "./styles.css";

class List extends Component {
  render() {
    return <h1>Lista de Repositórios</h1>;
  }
}

export default List;
```

Note que este componente é um componente preparado para trabalhar com estados!

Agora vamos utilizar o `componentDidMount(){}` para fazer a "busca" na api e alterar o estado deste componente, assim que obtiver estes dados.

**src/components/List/index.js**

```js
import React, { Component, Fragment } from "react";
import api from "../../services/api";
import "./styles.css";

class List extends Component {
  state = {
    repos: []
  };
  componentDidMount() {
    this.loadRepos();
  }
  loadRepos = async () => {
    const response = await api.get();
    this.setState({ repos: response.data });
  };
  render() {
    return (
      <Fragment>
        <h1>Lista de Repositórios</h1>
        <ul>
          {(this.state.repos.length &&
            this.state.repos.map((item, key) => {
              return (
                <li key={key}>
                  <a
                    href={item.html_url}
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    {item.name}
                  </a>
                </li>
              );
            })) || <li>Carregando...</li>}
        </ul>
      </Fragment>
    );
  }
}

export default List;
```

Como sabemos JavaScript é uma linguagem assíncrona, por isso, existem várias formas de se obter uma informação sem uma sincronissidade.

Note que criamos uma função chamada `this.loadRepos()` essa função será o gatilho para a busca na api. Um detalhe interessante aqui é que essa é uma função do tipo `async` o que significa, que ela pode "esperar" por promisses serem resolvidas, que é exatamente o nosso caso! Note que em: `const response = await api.get();` estamos fazendo com que essa linha "aguarde" a resolução da promise criada pelo axios, com os resultados esperados e só na sequência eh que os dados irão popular o estado do componente.

Note também que, estamos utilizando isso a nosso favor para fazer um sistema de Loading. Ou seja, dentro do `render()` nós iremos sempre verificar... se tivermos dados no estado, imprimos estes dados, caso contrário imprimimos uma mensagem `Carregando...`

Fazemos a verificação: se o estado está preenchido com ítens, então faça um map destes ítens retornando para cada ocorrência um elemento de lista. Se não, retorne um elemento de lista com "carregando..."

Agora, podemos colocar um estilo para melhorar um pouco o visual da lista de repositórios:

**src/components/List/styles.css**

```css
h1.repos {
  text-align: center;
  margin-top: 30px;
  margin-bottom: 20px;
  text-transform: uppercase;
  padding-bottom: 10px;
}

#repos-list {
  max-width: 700px;
  margin: 20px auto 0;
  padding: 0 20px;
}

#repos-list article {
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 20px;
  margin-bottom: 20px;
}

#repos-list article strong {
  font-size: 1.2rem;
}

#repos-list article p {
  font-size: 1rem;
  color: #999;
  margin-top: 5px;
  line-height: 24px;
}

#repos-list article a {
  height: 42px;
  border-radius: 5px;
  border: 1px solid #da552f;
  background: none;
  margin-top: 20px;
  color: #da552f;
  font-weight: bold;
  font-size: 1rem;
  text-decoration: none;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2s;
}

#repos-list article a:hover {
  background: #da552f;
  color: #fff;
}
```

E desta forma, temos um componente que exibe os dados remotos obtidos através de uma API.

## Módulo 5 - Eventos

No ReactJS, temos uma forma bem elegante de ativar determinados eventos. Os eventos basicamente são as **ações** que os usuários podem tomar em nossa aplicação, como por exemplo: o clicar de um botão, o passar do mouse em uma imagem ou fazer o scroll da página.

A forma de capturar um evento no ReactJS pode ser feita da seguinte forma por exemplo:

```js
...
<button onClick={executarFuncaoDoBotao()}></button>
```

Seguindo com o nosso exemplo, vamos adicionar 2 novos componentes na nossa lista de repositórios. Um **button** e um **input**. A idéia agora é transformar o projeto para que ele possa pegar os repositórios de qualquer usuário informado neste input.

**src/components/Button/index.js**

```js
import React from "react";
import "./styles.css";

const Button = props => <button className="btn">Filtrar</button>;

export default Button;
```

**src/components/Button/styles.css**

```css
.btn {
  cursor: pointer;
  height: 42px;
  border-radius: 5px;
  border: 1px solid #da552f;
  background: none;
  margin-top: 20px;
  background: #da552f;
  color: #fff;
  font-weight: bold;
  font-size: 1rem;
  text-decoration: none;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2s;
  width: 280px;
  text-transform: uppercase;
}

.btn:hover {
  background: #fff;
  color: #da552f;
}
```

Para entender a utilização dos enventos poderíamos por exemplo demonstrar o mesmo botão com uma funcionalidade:

```js
import React from "react";
import "./styles.css";

const myButton = () => {
  console.log("Alguém clicou!");
};

const Button = () => (
  <button className="btn" onClick={myButton}>
    Meu botão
  </button>
);

export default Button;
```

Note que, quando o botão for clicado, uma mensagem será exibida no console da aplicação.

Vamos então criar o componente de Input.

**/src/components/Input/index.js**

```js
import React from "react";
import "./styles.css";

const Input = () => (
  <input type="text" className="input" placeholder="Usuário" />
);

export default Input;
```

**/src/components/Input/styles.css**

```css
.input {
  height: 42px;
  border-radius: 5px;
  border: 1px solid #da552f;
  background: none;
  margin-top: 20px;
  color: #da552f;
  font-weight: bold;
  font-size: 1rem;
  text-decoration: none;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2s;
  width: 100%;
  margin-right: 10px;
  background-color: #fff;
}
```

Agora, podemos colocar estes 2 novos componentes em nosso componente principal com a listagem de repositórios, e analisar o seu comportamento visual.

**/src/components/List/index.js**

```js
import React, { Component, Fragment } from "react";
import api from "../../services/api";
import "./styles.css";
import Button from "../Button"; // Importando um Botão
import Input from "../Input"; // Importando um Input

class List extends Component {
  state = {
    repos: []
  };
  componentDidMount() {
    this.loadRepos();
  }
  loadRepos = async () => {
    const response = await api.get();
    this.setState({ repos: response.data });
  };
  render() {
    return (
      <Fragment>
        <h1 className="repos">Lista de Repositórios</h1>
        <div id="repos-filter">
          <Input />
          <Button />
        </div>
        <div id="repos-list">
          {(this.state.repos.length &&
            this.state.repos.map((item, key) => {
              return (
                <article key={key}>
                  <strong>{item.name}</strong>
                  <p>{item.description}</p>
                  <a
                    href={item.html_url}
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    Acessar Repositório
                  </a>
                </article>
              );
            })) || <p>Carregando...</p>}
        </div>
      </Fragment>
    );
  }
}

export default List;
```

E ajustar um pouco o CSS:

**src/components/List/styles.css**

```css
#repos-filter {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
}

#repos-list,
#repos-filter {
  max-width: 700px;
  margin: 20px auto 0;
  padding: 0 20px;
}
```

Com isso, já temos todo o **visual** da nossa aplicação finalizado.

Mas, note que... a aplicação não está eficiente. Imagine que nós tivessemos vários botões em nossa aplicação, não seria interessante ter que criar um componente para cada novo botão.

Por isso vamos aprender como passar propriedades entre nossos componentes. Para depois implementar as funcionalidades da aplicação.

Sem contar que... por enquanto o botão ainda não faz nada!

## Módulo 6 - Propriedades

É a principal forma de comunicação entre os componentes.

Dentro de um componente, nós recebemos um objeto `props` e neste objeto teremos todos os valores passados por argumento do componente, por exemplo:

```js
<div id="repos-filter">
  <Input mensagem="Digite um usuário..." />
  <Button>Filtar</Button>
</div>
```

Node que aqui, queremos passar **atributos** e **filhos** para os nossos componentes, assim como estamos acostumados a fazer com o próprio HTML.

Poderíamos então em cada um dos componentes, utilizar esses valores da seguinte forma:

```js
import React from "react";
import "./styles.css";

const Input = props => (
  <input type="text" className="input" placeHolder={props.label} />
);

export default Input;
```

ou ainda, trabalhar com o _children_ que representa o valor passado como "conteúdo" do componente

```js
import React from "react";
import "./styles.css";

const Button = props => <button className="btn">{props.children}</button>;

export default Button;
```

Desta forma, temos agora componentes que podem ter comportamentos visuais iguais, mas com conteúdos diferentes, ótimos para o conceito de **modularição** das nossas páginas web.

## Módulo 7 - Passando Funções por Propriedades

Se nós podemos passar quaisquer parâmetros para os nossos componentes, também podemos passar funções. Para demonstrar isso, vamos imaginar que queremos ao clicar do botão, mostrar uma mensagem no console, poderíamos então fazer algo do tipo:

```js
import React, { Component, Fragment } from "react";
import api from "../../services/api";
import "./styles.css";
import Button from "../Button";
import Input from "../Input";

class List extends Component {
  state = {
    repos: []
  };
  componentDidMount() {
    this.loadRepos();
  }
  loadRepos = async () => {
    const response = await api.get();
    this.setState({ repos: response.data });
  };
  handleButtonClick = () => {
    // Função que será chamada
    console.log("clicou");
  };
  render() {
    return (
      <Fragment>
        <h1 className="repos">Lista de Repositórios</h1>
        <div id="repos-filter">
          <Input label="Filtar" />
          <Button onClick={this.handleButtonClick}>Filtrar</Button>
        </div>
        <div id="repos-list">
          {(this.state.repos.length &&
            this.state.repos.map((item, key) => {
              return (
                <article key={key}>
                  <strong>{item.name}</strong>
                  <p>{item.description}</p>
                  <a
                    href={item.html_url}
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    Acessar Repositório
                  </a>
                </article>
              );
            })) || <p>Carregando...</p>}
        </div>
      </Fragment>
    );
  }
}

export default List;
```

E no botão...

```js
import React from "react";
import "./styles.css";

const Button = props => (
  <button className="btn" onClick={props.onClick}>
    {props.children}
  </button>
);

export default Button;
```

Aqui é importante entender que as função são passadas como parâmetro. E pode parecer meio confuso a primeira vista. Pois, o componente de botão irá "executar" uma função que foi definida em um componente "fora" dele. E é isso mesmo! É assim que nós fazemos com que os componentes transfiram as responsabilidades.

A idéia agora é criar um novo atributo no estado da lista chamado _filter_. Este elemento deverá ser alterado quando algo for digitado no input. Isso vai facilitar bastante a manipulação deste elemento.

Podemos então entender que no ReactJS, podemos criar statos para "representar" cada um dos "valores" dos componentes visuais que serão apresentados na tela. Ou seja, se temos um `<Input>` vamos ter um atributo no estado correspondente para o valor deste `<Input>`.

**src/components/List/index.js**

```js
import React, { Component, Fragment } from "react";
import api from "../../services/api";
import "./styles.css";
import Button from "../Button";
import Input from "../Input";

class List extends Component {
  state = {
    filter: "diogocezar", // Deve ser alterado sempre que o input for alterado
    repos: []
  };
  componentDidMount() {
    this.loadRepos();
  }
  loadRepos = async () => {
    const response = await api.get();
    this.setState({ repos: response.data });
  };
  handleButtonClick = () => {
    console.log("clicou");
  };
  handleChangeInput = e => {
    // Faz a alteração quando o input for alterado
    this.setState({ filter: e.target.value });
  };
  render() {
    return (
      <Fragment>
        <h1 className="repos">Lista de Repositórios {this.state.filter}</h1>
        <div id="repos-filter">
          <Input label="Filtar" onChange={this.handleChangeInput} />
          <Button onClick={this.handleButtonClick}>Filtrar</Button>
        </div>
        <div id="repos-list">
          {(this.state.repos.length &&
            this.state.repos.map((item, key) => {
              return (
                <article key={key}>
                  <strong>{item.name}</strong>
                  <p>{item.description}</p>
                  <a
                    href={item.html_url}
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    Acessar Repositório
                  </a>
                </article>
              );
            })) || <p>Carregando...</p>}
        </div>
      </Fragment>
    );
  }
}

export default List;
```

**src/components/Input/index.js**

```js
import React from "react";
import "./styles.css";

const Input = props => (
  <input
    type="text"
    className="input"
    placeholder={props.label}
    value={props.value}
    onChange={props.onChange}
  />
);

export default Input;
```

Desta forma, sempre que nós alterarmos o conteúdo do input, a função de onChange é executada. Essa função, chama a função do componente externo, que altera o estado do componente `List`, alterando o `filter` para o que foi digitado.

Agora precisamos de fato fazer a busca por uma url que utilize o filtro.

Para isso, vamos alterar a função `loadRepos`

```js
loadRepos = async () => {
  const url = `${this.state.filter}/repos`;
  const response = await api.get(url);
  this.setState({ repos: response.data });
};
```

Note que agora, estamos alterando a forma como a URL deverá ser montado, por isso também precisaremos alterar o baseURL da `api.js`.

Além disso, estamos utilizando o atributo do estado chamado `filter` para compor a URL em questão.

**services/api.js**

```js
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.github.com/users" // Alteração da URL para compor no componente
});

export default api;
```

e finalmente, alterar a ação do botão:

```js
handleButtonClick = () => {
  this.loadRepos();
};
```

Com isso, cobrimos as principais funcionalidades para a crição de uma aplicação react.

Mas, nossa aplicação ficou toda em uma única página. E essa é a ideia, manter tudo em uma única página, mas... como fazer para que quando o usuário acesse uma outra rota, por exemplo /contato ou /blog algo diferente seja exibido na tela?

Lembra? Esse era o princípio de uma SPA! Para isso, precisaremos estudar um outro conjunto de componentes.

Eles serão o responsáveis por mostrar componentes diferentes com base na rota que for acessada.

Faremos na sequência então, uma página interna para exibição dos detalhes dos repositórios.

## Módulo 8 - Rotas

O primeiro passo para nós criarmos nossas rotas é instalar um novo pacote em nosso projeto, para isso:

```bash
yarn add react-router-dom
```

Com isso, estamos prontos para fazer algumas modificações em nosso projeto.

O primeiro passo é criar um componente principal chamado `Routes` e dizer ao `index.js` que este será componente principal a ser chamado.

Então...

Criar em **/src/routes/index.js**

```js
import React, { Component } from "react";
import { BrowserRouter, Switch, Route } from "react-router-dom";

import Main from "../pages/Main";

class Router extends Component {
  render() {
    return (
      <BrowserRouter>
        <Switch>
          <Route exact path="/" component={Main} />
        </Switch>
      </BrowserRouter>
    );
  }
}

export default Router;
```

Note que estamos criando um componente que irá ser o nosso **gerenciador** de rotas de nossa aplicação, neste exemplo, estamos dizendo que quando a rota for exatamente igual a `/` nós iremos renderizar na tela o nosso componente `Main`, já conhecido.

Mas vamos melhorar isso um pouco, e criar uma outra página de exemplo, apenas para testar se o sistema de rotas irá funcionar corretamente.

**/src/pages/About/index.js**

```js
import React, { Fragment } from "react";
import Header from "../../components/Header";
import "./styles.css";
const About = () => {
  return (
    <Fragment>
      <Header />
      <h1>Sobre o Sistema de Repositórios do Git</h1>
    </Fragment>
  );
};
export default About;
```

E nosso arquivo de rotas deve ficar desta forma:

```js
import React, { Component } from "react";
import { BrowserRouter, Switch, Route } from "react-router-dom";

import Main from "../pages/Main";
import About from "../pages/About";

class Router extends Component {
  render() {
    return (
      <BrowserRouter>
        <Switch>
          <Route exact path="/" component={Main} />
          <Route path="/about" component={About} />
        </Switch>
      </BrowserRouter>
    );
  }
}

export default Router;
```

Agora que temos mais que uma página, pode ser conveniente melhorar um pouco a organização dos CSS's e criar um css global para toda aplicação e importá-lo no `index.js` principal da aplicação.

**/src/styles/index.css**

```css
* {
  margin: 0;
  padding: 0;
  outline: 0;
  box-sizing: border-box;
}

:root {
  font-size: 14px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  background: #fafafa;
  color: #333;
}
```

E agora o importamos em:

**src/index.js**

```js
import React from "react";
import ReactDOM from "react-dom";
import Routes from "./routes";
import "./styles/index.css";

ReactDOM.render(<Routes />, document.getElementById("root"));
```

E então não precisamos do arquivo `src/pages/Main/styles.css`.

O arquivo `src/pages/About/styles.css` ficará com um simples estilo:

```css
h1 {
  margin-top: 30px;
  text-align: center;
}
```

Agora, vamos "fechar" nosso sistema de exemplo com a criação de uma rota para exibir os detalhes de um repositório.

Para isso, vamos criar um novo componente de página e configurar sua rota:

**/src/pages/Details/index.js**

```js
import React, { Fragment } from "react";
import Header from "../../components/Header";
import "./styles.css";
const Details = () => {
  return (
    <Fragment>
      <Header />
      <h1>Detalhes de um Repositório</h1>
    </Fragment>
  );
};
export default Details;
```

E nas rotas:

```js
import React, { Component } from "react";
import { BrowserRouter, Switch, Route } from "react-router-dom";

import Main from "../pages/Main";
import About from "../pages/About";
import Details from "../pages/Details";
import Header from "../components/Header";

class Router extends Component {
  render() {
    return (
      <BrowserRouter>
        <Header />
        <Switch>
          <Route exact path="/" component={Main} />
          <Route path="/about" component={About} />
          <Route exact path="/details/:user/:id" component={Details} />
        </Switch>
      </BrowserRouter>
    );
  }
}

export default Router;
```

Note que agora, para a rota de detalhes, estamos ainda definindo dois outros parâmetros chamados `user` e `id` que serão os responsáveis por buscar os dados de um repositório e mostrá-lo na tela.

Ainda... mudamos um pouco a estrutura dos componentes a serem exibidos.

Colocamos o `<Clock>` dentro de `<Header>` e o `<Header>` direto no componente das rotas.

Agora podemos analisar como fica o componente para exibir os detalhes de um repositório:

```js
import React, { Component, Fragment } from "react";
import "./styles.css";
import api from "../../services/api";
import { Link } from "react-router-dom";
class Details extends Component {
  state = {
    repo: null
  };
  componentDidMount() {
    const id = this.props.match.params.id;
    const user = this.props.match.params.user;
    this.loadRepoById(id, user);
  }
  async loadRepoById(id, user) {
    const url = `${user}/repos`;
    const response = await api.get(url);
    const repo = response.data.find(
      item => item.id.toString() === id.toString()
    );
    this.setState({ repo: repo });
  }
  render() {
    const repo = this.state.repo;
    return (
      <Fragment>
        <h1>Detalhes de um Repositório</h1>
        <div id="repos-details">
          {repo && (
            <article>
              <strong>{repo.name}</strong>
              <p>{repo.description}</p>
              <a href={repo.html_url} target="_blank" rel="noopener noreferrer">
                Acessar Repositório
              </a>
              <Link to="/">Voltar</Link>
            </article>
          )}
        </div>
      </Fragment>
    );
  }
}
export default Details;
```

Note que obtemos os dados dos parmâmetros com:

```js
const id = this.props.match.params.id;
const user = this.props.match.params.user;
```

Depois, executamos o loading e procuramos apenas o elemento que tem o `id` passado como parâmetro:

```js
  async loadRepoById(id, user) {
    const url = `${user}/repos`;
    const response = await api.get(url);
    const repo = response.data.find(
      item => item.id.toString() === id.toString()
    );
    this.setState({ repo: repo });
  }
```

Colocando este elemento no estado do componente.

Por fim, nós temos que exibir os detalhes, para isso, uma rápida "copiada" no estilo já definido para o `<List>`.

```css
h1 {
  margin-top: 30px;
  text-align: center;
}

#repos-details {
  max-width: 700px;
  margin: 20px auto 0;
  padding: 0 20px;
}

#repos-details article {
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 20px;
  margin-bottom: 20px;
}

#repos-details article strong {
  font-size: 1.2rem;
}

#repos-details article p {
  font-size: 1rem;
  color: #999;
  margin-top: 5px;
  line-height: 24px;
}

#repos-details article a {
  height: 42px;
  border-radius: 5px;
  border: 1px solid #da552f;
  background: none;
  margin-top: 20px;
  color: #da552f;
  font-weight: bold;
  font-size: 1rem;
  text-decoration: none;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2s;
}

#repos-details article a:hover {
  background: #da552f;
  color: #fff;
}
```

Notemos também a utilização do componente `<Link>` do `react-router-dom` para a alteração das rotas dentro do sistema, neste caso, para voltar para a página anterior.

E por fim, uma modificação na página principal, para que ao invés de apontar para o repositório nós apontemos para a nossa página interna.

```js
import React, { Component, Fragment } from "react";
import api from "../../services/api";
import "./styles.css";
import Button from "../Button";
import Input from "../Input";
import { Link } from "react-router-dom";

class List extends Component {
  state = {
    filter: "diogocezar",
    repos: []
  };
  componentDidMount() {
    this.loadRepos();
  }
  loadRepos = async () => {
    const url = `${this.state.filter}/repos`;
    const response = await api.get(url);
    this.setState({ repos: response.data });
  };
  handleButtonClick = () => {
    this.loadRepos();
  };
  handleChangeInput = e => {
    this.setState({ filter: e.target.value });
  };
  render() {
    return (
      <Fragment>
        <h1 className="repos">Lista de Repositórios {this.state.filter}</h1>
        <div id="repos-filter">
          <Input label="Filtar" onChange={this.handleChangeInput} />
          <Button onClick={this.handleButtonClick}>Filtrar</Button>
        </div>
        <div id="repos-list">
          {(this.state.repos.length &&
            this.state.repos.map((item, key) => {
              return (
                <article key={key}>
                  <strong>
                    {item.name} - {item.id}
                  </strong>
                  <p>{item.description}</p>
                  <Link to={`/details/${this.state.filter}/${item.id}`}>
                    Detalhes
                  </Link>
                </article>
              );
            })) || <p>Carregando...</p>}
        </div>
      </Fragment>
    );
  }
}
export default List;
```

Com isso, fechamos os principais conceitos sobre React. E agora estamos pronto para conhecer expandir os conhecimentos sobre como aprimorar a parte visual dos nossos componentes com **Styleds Components**.

## Módulo 9 - Styled Components

- Site oficial: https://www.styled-components.com/
- Documentação: https://www.styled-components.com/docs

### Como é o padrão do React?

- Temos arquivos "puros" .css para estilização dos componentes;
- Dentro dos arquivos .js nós importamos o css em questão para estilizar arquivos;
- Utiliza-se as "classes" ou "id" ou "seletores" para personalizar a aparência do seu projeto;
- Muito próximo do que nós já conhecemos com HTML + CSS :blush:

Com **styled-components**, isso passa a ser diferente!

- Cria NOVOS componentes;
- Sua única e exclusiva função é: a sua estilização! :open_mouth:
- Ao invés de usar tags nativas e classes, vamos usar componentes em React com a única diferença que eles já terão por definição um estilo;

Vamos a um exemplo simples!

```js
import React, { Component } from "react";
import { Title } from "./styles";
class App extends Component {
  render() {
    return (
      <div>
        <Title>Hello World</Title>
      </div>
    );
  }
}
export default App;
```

Note que agora, não temos mais um arquivo .css e sim um arquivo .js que será o responsável por retornar os componentes estilizados prontos para uso.

```js
import styled from "styled-components"; // importa o pacote
const Title = styled.h1`
  color: #f00;
`;
export { Title };
```

- Note que: criamos uma variável que recebe uma função styled;
- Essa função é uma função "especial" da linguagem JavaScript moderna que permite que uma função se comporte como uma string;
- Essa técnica se chama Tagged template strings: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/template_strings#Tagged_template_strings
- No VSCode para ver a sintaxe com hightlight precisa-se uma extensão: styled-components;

### Tá... e pq?

O bacana é que ao utilizar **styled-components** nós temos a certeza que uma estilização nunca vai afetar outro componente da nossa aplicação, eles são _autocontidos_.

O nome disso no CSS é CSS Escopado! É o estilo que pertence ao escopo!

Quando temos várias classes, geralmente essas classes tem nomes iguais... Exemplo: "btn-1", "big-image", etc...

Por isso, conseguimos reaproveitar de VERDADE componentes de um projeto em outro! Sem a interdependência de outros arquivos CSS!

### Sintaxe Hierárquica

Conseguimos aninhar nossas propriedades de acordo com a estrutura de componentes:

```js
import React, { Component } from "react";
import { Title } from "./styles";
class App extends Component {
  render() {
    return (
      <div>
        <Title>
          Hello World
          <span>texto menor</span>
        </Title>
      </div>
    );
  }
}
export default App;
```

```js
import styled from "styled-components"; // importa o pacote
const Title = styled.h1`
  color: #f00;
  span {
    font-size: 12px;
  }
`;
export { Title };
```

- Vantagem: não precisamos criar um componente para TODA a estilização que formos fazer! Só quando fizer sentido!
- Quando criar um novo? Quando tivermos blocos! Exemplo: Formulários, Seção de Destques de uma Home;

### Passando Props

E quando temos a necessidade de criar diferentes estilos para o mesmo componente?

Por exemplo botões:

- Um botão padrão;
- Um botão de warning;
- Um botão de error;
- Um botão maior;
- Um botão menor;
- Etc...

```js
import React, { Component } from "react";
import { Title } from "./styles";
class App extends Component {
  render() {
    return (
      <div>
        <Title fontSize={20}>
          Hello World
          <span>texto menor</span>
        </Title>
      </div>
    );
  }
}
export default App;
```

```js
import styled from "styled-components"; // importa o pacote
const Title = styled.h1`
  color: #f00;
  font-size: ${props => `${props.fontSize}px`};
  span {
    font-size: 12px;
  }
`;
export { Title };
```

Conseguimos então acessar facilmente as propriedades dos styleds components;

### Herança de Propriedades

Uma funcionalidade muito bacana também é a possibilidade de herdar as propriedades de um outro styled-component.

```js
import React, { Component } from "react";
import { Title, TitleSmall } from "./styles";
class App extends Component {
  render() {
    return (
      <div>
        <Title fontSize={20}>
          Hello World
          <span>texto menor</span>
        </Title>
        <TitleSmall>
          Novo Título Pequeno
          <span>texto menor</span>
        </TitleSmall>
      </div>
    );
  }
}
export default App;
```

```js
import styled from "styled-components"; // importa o pacote
const Title = styled.h1`
  color: #f00;
  background: #000;
  font-size: ${props => `${props.fontSize}px`};
  span {
    font-size: 12px;
  }
`;

const TitleSmall = style(Title)`
    color: #00f;
    font-size: 16px;
`;
export { Title, TitleSmall };
```

### Conclusão

Com essa demonstração vimos o poder dos styled-components;

É importante lembrar que aprender styled-componente não tira a necessidade de aprender CSS, que é a base para a criação de suas propriedades;

Também, temos de fato componentes totalmente modulares que podem ser "copiados" para novos projetos;

Uma ótima maneira de criar suas próprias libs de componentes visuais;

## Módulo 10 - Hooks

A versão 16.8 do React nos trouxe uma funcionalidade super interessante para nós. Os **Hooks**.
Os hooks nos permitem gerenciar o estado de um componente dentro de funções, não sendo mais necessário criar uma classe para isso. Como isso funciona?

Exemplo apresentado no Módulo 2, sem os hooks.

```js
import React, { Component } from "react";

class App extends Component {
  state = {
    result: 0
  };
  soma = (a, b) => {
    this.setState({ result: a + b });
  };
  render() {
    return <h1>Soma é {this.state.result}</h1>;
  }
}

export default App;
```

E agora o mesmo exemplo, utilizando os hooks.

```js
import React, { useState } from "react";

const App = () => {
  const [result, setResult] = useState(0);

  const soma = (a, b) => {
    setResult(a + b);
  };

  return <h1>Soma é {result}</h1>;
};

export default App;
```

Agora nossa classe App se tornou uma função, e o estado passa a ser gerenciado pela função useState.

Criamos uma variável de estado da seguinte maneira

```js
const [result, setResult] = useState(0);
```

No código acima nós criamos um 'atributo' chamado 'result'.
A função **useState(initialState)** nos dá os mesmos poderes que o **this.state** e podemos definir qualquer valor inicial, passando-o por parâmetro, bem ali no lugar do initialState.

Essa função retorna um array, e utilizando a destruturação do ES6 conseguimos obter partes do array onde, no primeiro indice obtemos o valor do estado e no segundo uma função que nos permite atualizar o valor do estado 'results'.

Agora para criarmos mais um atributo de estado basta adicionar um novo useState().

```js
const [result, setResult] = useState(0);
const [otherState, setOtherState] = useState("initial value");
```

Para alterar o valor de 'results' basta chamar a função 'setResult(newState)' e para alterar 'otherState' chamamos 'setOtherState(newState)'

Agora você já sabe gerenciar estados com **hooks**!!
Mas espera aí! Se com os hooks não temos mais classes, como utilizamos o método 'componentDidMount()'?
Para resolver esse problema vamos ver uma nova função dos hooks o **useEffect**

Exemplo do módulo 2:

```js
import React, { Component } from "react";

class Clock extends Component {
  state = {
    now: null
  };

  componentDidMount() {
    setInterval(() => {
      this.setState({ now: new Date().toLocaleTimeString() });
    }, 1000);
  }

  render() {
    return <h1 className="clock">{this.state.now}</h1>;
  }
}

export default Clock;
```

Com Hooks:

```js
import React, { useState, useEffect } from "react";

const Clock = () => {
  const [now, setNow] = useState(null);

  useEffect(() => {
    setInterval(() => {
      setNow(new Date().toLocaleTimeString());
    }, 1000);
  }, []);

  return <h1 className="clock">{now}</h1>;
};

export default Clock;
```

A função 'useEffect()' recebe dois parâmetros, o primeiro é uma função e podemos pensar nela como sendo o corpo do nosso componentDidMount() e o segundo parâmetro define quando essa função deve ser executada. Para que nosso useEffect() seja executado somente na inicialização do componente podemos passar um array vazio como segundo parâmetro.
Pronto! Agora já temos o nosso antigo 'componentDidMount()'.

## Módulo 11 - Redux

> Baseado em: https://www.youtube.com/watch?v=u99tNt3TZf8&t=1281s

O Redux é utilizado no momento em que nós precisamos gerenciar os dados da nossa aplicação.

Podem ser informações vindas das entradas dos nossos usuários, de uma api, ou de outros componentes.

Também nos ajuda a gerenciar como os componentes devem se comportar em relação as ações dos usuários.

Mas quando é necessário utilizar o Redux?

Basicamente quando nossa aplicação escala em um nível no qual não conseguimos mais gerenciar as passagens de props entre os componentes.

Imagine uma situação de componentes encadeados. Seria bem complicado e de difícil manutenção propagar um atributo entre todos os níveis de encadementos destes componentes.

Por isso, a proposta da utilização do Redux é a centralização de todas as informações em um único gerenciador de estados.

Imagine que, com o redux, nós teríamos um componente responsável por gerenciar os estados que são compartilhados entre todos os componentes.

Para os exemplos deste módulo, vamos trabalhar com um novo projeto específico para o redux, para isso, criaremos com o `create-react-app` um novo projeto chamado
`react-redux`

```bash
create-react-app react-redux
```

na sequência devemos instalar dois pacotes que serão essenciais para a utilização do redux:

```bash
yarn add redux react-redux
```

Vamos novamente, apagar alguns arquivos que não serão utilizados, deixando a estrutura da seguinte forma:

```
src
|-- App.js
`-- index.js
```

Vamos imaginar agora uma estrutura específica para esta aplicação de exemplo. Teremos dois componentes principais, uma `SideBar` com módulos e vídeos de um curso, e um componente de `Vídeo` que além de exibir o vídeo em questão, também deveria mostrar o título de vídeo e a que módulo ele pertence.

Em uma organização inicial, poderiamos pensar nos seguintes componentes e seus respectivos conteúdos:

```
.
|-- App.js
|-- components
|   |-- SideBar
|   |   `-- index.js
|   `-- Video
|       `-- index.js
`-- index.js
```

**App.js**

```js
import React, { Fragment } from "react";
import SideBar from "./components/SideBar";
import Video from "./components/Video";

function App() {
  return (
    <Fragment>
      <h1>React + Redux</h1>
      <Video />
      <SideBar />
    </Fragment>
  );
}

export default App;
```

**SideBar/index.js**

```js
import React, { Component } from "react";

export default class SideBar extends Component {
  state = {
    modules: [
      {
        id: 1,
        title: "Modulo 1",
        lessons: [
          {
            id: 1,
            title: "Primeiro vídeo do módulo 1"
          },
          {
            id: 2,
            title: "Segundo vídeo do módulo 1"
          }
        ]
      },
      {
        id: 2,
        title: "Modulo 2",
        lessons: [
          {
            id: 1,
            title: "Primeiro vídeo do módulo 2"
          },
          {
            id: 2,
            title: "Segundo vídeo do módulo 2"
          }
        ]
      }
    ]
  };
  render() {
    const { modules } = this.state;
    return (
      <aside>
        {modules.map(module => {
          return (
            <div key={module.id}>
              <strong>{module.title}</strong>
              <ul>
                {module.lessons.map(lesson => {
                  return <li key={lesson.id}>{lesson.title}</li>;
                })}
              </ul>
            </div>
          );
        })}
      </aside>
    );
  }
}
```

**Video/index.js**

```js
import React from "react";

const Video = () => (
  <div>
    <h1>Módulo x</h1>
    <h2>Vídeo x</h2>
  </div>
);

export default Video;
```

Note que a aplicação já tem uma estrutura bacana, e faz sentido.

Mas ai vem a pergunta: Como compartilhar as informações do estado da SideBar com o componente de Video?

Uma forma "tradicional" seria alterar a "fonte" de informação para um componente pai, que pudesse distribuir os estados entre os dois componentes, nessa caso, faria sentido colocar o estado no componente `App`

Poderíamos então considerar o uma possível modificação:

```js
import React, { Component, Fragment } from "react";
import SideBar from "./components/SideBar";
import Video from "./components/Video";

export default class SideBar extends Component {
  state = {
    activeLesson: null,
    activeModule: null,
    modules: [
      {
        id: 1,
        title: "Modulo 1",
        lessons: [
          {
            id: 1,
            title: "Primeiro vídeo do módulo 1"
          },
          {
            id: 2,
            title: "Segundo vídeo do módulo 1"
          }
        ]
      },
      {
        id: 2,
        title: "Modulo 2",
        lessons: [
          {
            id: 1,
            title: "Primeiro vídeo do módulo 2"
          },
          {
            id: 2,
            title: "Segundo vídeo do módulo 2"
          }
        ]
      }
    ]
  };
  render(){
    return (
      <Fragment>
        <h1>React + Redux</h1>
        <Video activeLesson={this.state.activeLesson} activeModule={this.state.activeModule}/>
        <SideBar modules={this.state.modules}/>
      </Fragment>
    )
  }
}

export default App;
```

É possível perceber neste simples exemplo que a complexidade começa a aumentar. Precisamos passar informações entre as propriedades e deslocar os estados para que eles façam sentido dos pais para os filhos.

Até aqui oks! Mas e se nós tivessemos 10 ou 15 níveis de componentes aninhados? Como gerenciar onde ficaram os estados? E como trabalhar com as passagens da funções? Um tanto quando complicado e trabalhoso!

**Então vamos ao redux!**

As organizações são as mais variadas, e vão de acordo com o gosto do freguês, mas neste exemplo, vamos tentar focar em uma organização mais "padrão".

Na raiz do projeto, devemos criar uma pasta chamada `store` e dentro dela um arquivo chamado `index.js`

**/store/index.js**

```js
import { createStore } from "redux";
const store = createStore();
export default store;
```

A função `createStore` vai criar um estado global para a nossa aplicação. Ela necessita de uma função como parâmetro que vai definir o estado inicial da nossa aplicação.

No nosso caso, nesse primeiro momento, queremos compartilhar apenas os nossos módulos, então, uma versão inicial poderia ser:

```js
import { createStore } from "redux";
function reducer() {
  return [
    {
      id: 1,
      title: "Modulo 1",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 1"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 1"
        }
      ]
    },
    {
      id: 2,
      title: "Modulo 2",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 2"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 2"
        }
      ]
    }
  ];
}
const store = createStore(reducer);
export default store;
```

Agora, precisamos de alguma forma de "importar" esse estado global para nossa aplicação. Por isso em `App.js` precisaremos importar um `Provider` do `react-redux`

```js
import React from "react";
import { Provider } from "react-redux";
import SideBar from "./components/SideBar";
import Video from "./components/Video";
import store from "./store";

function App() {
  return (
    <Provider store={store}>
      <h1>React + Redux</h1>
      <Video />
      <SideBar />
    </Provider>
  );
}

export default App;
```

Neste ponto, já temos a store sendo compartilhada entre os componentes. Mas agora precisamos transformar os componentes para "ler" e "escrever" nestes estado global.

Para isso, vamos utilizar o `connect`.

A função `connect` irá receber como parâmetro o estado compartilhado, e nós devemos retornar quais deles nós queremos compartilhar com o componente!

Conectando o `SideBar`, ficaríamos com uma estrutura parecida com essa:

```js
import React, { Component } from "react";
import { connect } from "react-redux";

class SideBar extends Component {
  render() {
    const { modules } = this.props;
    return (
      <aside>
        {modules.map(module => {
          return (
            <div key={module.id}>
              <strong>{module.title}</strong>
              <ul>
                {module.lessons.map(lesson => {
                  return <li key={lesson.id}>{lesson.title}</li>;
                })}
              </ul>
            </div>
          );
        })}
      </aside>
    );
  }
}

export default connect(state => ({ modules: state }))(SideBar);
```

A partir disso, temos como `props` deste componente os módulos mapeados de forma global.

Agora precisamos fazer com que quando um usuário clicar em um componente da lista, Este vídeo fique marcado como princial e isso reflita diretamente no estado global, e também deverá ser propagado para o Vídeo;

Então o primeiro passo para a organização do `reducer` é transformado em um objeto armazenará os modulos e vídeos (como já temos) mas também irá armazenar qual é o elemento _ativo_.

Nossa store ficaria então:

```js
import { createStore } from "redux";
function reducer() {
  return {
    activeLesson: null,
    activeModule: null,
    modules : [
      {
      id: 1,
      title: "Modulo 1",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 1"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 1"
        }
      ]
    },
    {
      id: 2,
      title: "Modulo 2",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 2"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 2"
        }
      ]
    }
  ]
}
const store = createStore(reducer);
export default store;
```

E agora no connect também temos que alterar para receber o objeto `modules`

```js
export default connect(state => ({ modules: state.modules }))(SideBar);
```

Agora vamos incluir um botão para _setar_ alguma lissão e módulo como ativos;

Mas como manipular os dados do _reducer_?

O reducer é uma função chave que é chamada automaticamente em alguns momentos da nossa aplicação.

Temos os reduces que já vimos anteiormente, nesta função global. Mas também temos um outro elmento chamado de _actions_. Essas actions são basicamente ações que nós repassamos para os nossos redux, indicando que nós precisamos manipular o estado global da nossa aplicação.

Queremos então, neste pequeno exemplo, que quando um botão seja clicado, nós alteremos as propriedades `activeLesson` e `activeModule` do nosso estado global.

Podemos então criar essa action, primeiramente dentro do nosso próprio componente:

```js
import React, { Component } from "react";
import { connect } from "react-redux";

const toggleLesson = (lesson, module) => {
  return {
    type: "TOGGLE_LESSON",
    module,
    lesson
  };
};

class SideBar extends Component {
  render() {
    const { modules, dispatch } = this.props;
    return (
      <aside>
        {modules.map(module => {
          return (
            <div key={module.id}>
              <strong>{module.title}</strong>
              <ul>
                {module.lessons.map(lesson => {
                  return (
                    <li key={lesson.id}>
                      {lesson.title}
                      <button
                        onClick={() => {
                          dispatch(toggleLesson(lesson, module));
                        }}
                      >
                        Acessar!
                      </button>
                    </li>
                  );
                })}
              </ul>
            </div>
          );
        })}
      </aside>
    );
  }
}

export default connect(state => ({ modules: state.modules }))(SideBar);
```

Note que a função de action, tem um formato padrão, que deve ser respeitado.

Agora precisamos de alguma forma _receber_ essa ação dentro do nosso reducer. Toda vez que houver um `dispatch` de uma ação o reducer irá atualizar seus dados novamente, assim como acontece com um componente que sempre entender uma modificação no estado o renderiza novamente.

Notemos agora que podemos interceptar novos 2 elementos no reducer:

```js
function reducer(state, action) ...
```

O estado é o estado anterior a execução da ação, e a ação é a ação em questão, que foi disparada de dentro do nosso componente.

Além disso é importante que nosso redux trabalhe com um estado inicial, que vai ser o primeiro estado quando nada tiver sido executado:

```js
import { createStore } from "redux";

const INITIAL_STATE = {
  activeLesson: null,
  activeModule: null,
  modules: [
    {
      id: 1,
      title: "Modulo 1",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 1"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 1"
        }
      ]
    },
    {
      id: 2,
      title: "Modulo 2",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 2"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 2"
        }
      ]
    }
  ]
};

function reducer(state = INITIAL_STATE, action) {
  return state;
}
const store = createStore(reducer);
export default store;
```

Note que colocamos todo o estado que tinhamos no retorno, para uma variável chamada `INITIAL_STATE`.

Note ainda que nós estamos recebendo um segundo parâmetro que irá respresentar a action que foi chamada.

Então poderíamos fazer do tipo:

```js
import { createStore } from "redux";

const INITIAL_STATE = {
  activeLesson: null,
  activeModule: null,
  modules: [
    {
      id: 1,
      title: "Modulo 1",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 1"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 1"
        }
      ]
    },
    {
      id: 2,
      title: "Modulo 2",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 2"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 2"
        }
      ]
    }
  ]
};

function reducer(state = INITIAL_STATE, action) {
  swtich(action.type){
    case 'TOGGLE_LESSON':
      return { ...state, activeLesson: action.payload.lesson, activeModule: action.module}
  }
  return state;
}
const store = createStore(reducer);
export default store;
```

Agora precisamos conectar o nosso outro componente de `Vídeo` para que ele possa receber também essas modificações globais.

Ficando da seguinte forma:

```js
import React from "react";
import { connect } from "react-redux";

const Video = props => {
  return (
    <div>
      {props.activeModule && <h1>Módulo {props.activeModule.title}</h1>}
      {props.activeLesson && <h1>Aula {props.activeLesson.title}</h1>}
    </div>
  );
};

export default connect(state => {
  return {
    activeLesson: state.activeLesson,
    activeModule: state.activeModule
  };
})(Video);
```

Mas essa forma de organizar o código, não é muito efeiciente! Podemos separar e organizar melhor nossas actions e reducers!

Nesse exemplos simples, nós cubrimos apenas uma funcionalidade da aplicação (a de aulas, vídeo e módulo), mas... imagine uma aplicação com várias responsabilidade, seria improdutivo manter tudo dentro de um mesmo reducer!

Então, agora... para melhorar as coisas definitivamente...

dentro da pasta `store` vamos criar uma pasta `reducers` e dentro desta pasta colocar todos os reducers da nossa aplicação. Neste nosso exemplo simples, vamos criar apenas um único reducer, chamado `course.js`. Dentro dele vamos copiar todo o conteúdo que havíamos colocado diretamente
no index.js da `store`.

```js
const INITIAL_STATE = {
  activeLesson: null,
  activeModule: null,
  modules: [
    {
      id: 1,
      title: "Modulo 1",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 1"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 1"
        }
      ]
    },
    {
      id: 2,
      title: "Modulo 2",
      lessons: [
        {
          id: 1,
          title: "Primeiro vídeo do módulo 2"
        },
        {
          id: 2,
          title: "Segundo vídeo do módulo 2"
        }
      ]
    }
  ]
};

const course = (state = INITIAL_STATE, action) => {
  console.log(action);
  switch (action.type) {
    case "TOGGLE_LESSON":
      console.log("passou");
      return {
        ...state,
        activeLesson: action.lesson,
        activeModule: action.module
      };
    default:
      return state;
  }
};

export default course;
```

Agora precisamos dentro da pasta reducers, criar um `index.js` na qual vamos "combinar" todos os reducers da nossa aplicação, neste caso apenas 1, o `course`.

```js
import { combineReducers } from "redux";
import course from "./course";

export default combineReducers({
  course
  // aqui poderiam vir outros!
});
```

A única diferença está na forma de chamar os reducers combinados, pois agora precisamos nos atentar que todos os conteúdos utilizados estão dentro do objeto `course` exportado pelo nosso `combineReducers`.

Agora precisamos fazer alguns ajustes!

**/src/store/index.js**

```js
import { createStore } from "redux";
import rootReducer from "./reducers";
const store = createStore(rootReducer);
export default store;
```

**src/components/SideBar/index.js**

```js
...
export default connect(state => ({ modules: state.course.modules }))(SideBar);
```

**src/components/Video/index.js**

```js
...
export default connect(state => {
  return {
    activeLesson: state.course.activeLesson,
    activeModule: state.course.activeModule
  };
})(Video);
```

Outro ponto a melhorar na nossa aplicação utilizando redux, seria melhorar a forma de trabalhar com as actions, pois, em algum momento mais de um componente pode querer utilizar a mesma action.

Para isso, vamos criar uma pasta de `action` em `src/store/actions` e dentro dela, podemos "copiar" o conteúdo que existia em `SideBar`

**/src/store/actions/course.js**

```js
const toggleLesson = (lesson, module) => {
  return {
    type: "TOGGLE_LESSON",
    module,
    lesson
  };
};
export { toggleLesson };
```

E ainda podemos deixar o código mais elegante...

```js
import React, { Component } from "react";
import { connect } from "react-redux";
import * as CourseActions from "../../store/actions/course";

class SideBar extends Component {
  render() {
    const { modules, toggleLesson } = this.props;
    return (
      <aside>
        {modules.map(module => {
          return (
            <div key={module.id}>
              <strong>{module.title}</strong>
              <ul>
                {module.lessons.map(lesson => {
                  return (
                    <li key={lesson.id}>
                      {lesson.title}
                      <button
                        onClick={() => {
                          toggleLesson(module, lesson);
                        }}
                      >
                        Acessar!
                      </button>
                    </li>
                  );
                })}
              </ul>
            </div>
          );
        })}
      </aside>
    );
  }
}

const mapStateToProps = state => ({
  modules: state.course.modules
});

const mapDispatchToProps = dispatch => ({
  toggleLesson: (module, lesson) =>
    dispatch(CourseActions.toggleLesson(lesson, module))
});

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(SideBar);
```

Note que agora criarmos funções especiais para ligar:

1. O estado global, com as propriedades do componente em questão;
2. As ações que alteram o esdo global, com propriedades do componente em questão;

E ainda temos mais uma ferrama bacana que nos ajudar montar o nosso `mapDispatchToProps`. Essa ferramente faz "automaticamente" to o processo visto anteiormente, para isso basta utilizar algo como:

```js
import React, { Component } from "react";
import { connect } from "react-redux";
import { bindActionCreators } from "redux";
import * as CourseActions from "../../store/actions/course";

class SideBar extends Component {
  render() {
    const { modules, toggleLesson } = this.props;
    return (
      <aside>
        {modules.map(module => {
          return (
            <div key={module.id}>
              <strong>{module.title}</strong>
              <ul>
                {module.lessons.map(lesson => {
                  return (
                    <li key={lesson.id}>
                      {lesson.title}
                      <button
                        onClick={() => {
                          toggleLesson(module, lesson);
                        }}
                      >
                        Acessar!
                      </button>
                    </li>
                  );
                })}
              </ul>
            </div>
          );
        })}
      </aside>
    );
  }
}

const mapStateToProps = state => ({
  modules: state.course.modules
});

const mapDispatchToProps = dispatch =>
  bindActionCreators(CourseActions, dispatch);

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(SideBar);
```

E assim terminamos o basicão do Redux. Não fica difícil de imaginar que para que este exemplo fosse mais "Real"o INITIAL_STATE, pudesse ser algo buscado de uma API, certo?

Pois então, o redux, nativamente não trabalha com requisiçõea assíncronas! Para que isso seja feito de forma eficiente, teríamos que trabalhabar com um middleware específico para este trabalho. Então, você pode seguir nos estudos com o **Thunk** ou o **Saga**, por exemplo.

---

Bom pessoal, é isso! Eu sinceramente espero que este material possa te ajudar de alguma forma ;)

Mas, tem MUITO mais coisas para se estudar :P
