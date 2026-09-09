# Javascript4Testers

Projeto de estudos do curso introdutório **Javascript4Testers** da QA Ninja (2021), para praticar os principais conceitos da linguagem e sua integração com páginas HTML por meio do **DOM (Document Object Model)**.

O projeto apresenta exemplos simples e práticos de variáveis, operadores, arrays, objetos, estruturas condicionais, funções, laços de repetição e manipulação de elementos HTML.

---

## 📚 Conteúdos estudados

- [Variáveis](#variáveis)
- [Operadores](#operadores)
  - [Operadores aritméticos](#operadores-aritméticos)
  - [Operadores de comparação](#operadores-de-comparação)
  - [Igualdade estrita](#igualdade-estrita)
  - [Operadores relacionais](#operadores-relacionais)
- [Arrays](#arrays)
- [Objetos](#objetos)
- [Funções](#funções)
- [Estruturas condicionais](#estruturas-condicionais)
  - [`if`, `else if` e `else`](#if-else-if-e-else)
  - [`switch`](#switch)
- [Laços de repetição](#laços-de-repetição)
  - [`for`](#for)
  - [`while`](#while)
  - [`forEach`](#foreach)
- [DOM — Document Object Model](#dom--document-object-model)
- [Integração entre HTML e JavaScript](#integração-entre-html-e-javascript)

---

## 🔤 Variáveis

Variáveis são utilizadas para armazenar valores que podem ser utilizados durante a execução do programa.

O JavaScript possui **tipagem dinâmica**, ou seja, o tipo da variável é determinado de acordo com o valor atribuído.

Exemplo:

```javascript
var numero = 10;

console.log(numero);
console.log(typeof numero);

var nome = "Carol";

console.log(typeof nome);
```

O operador `typeof` permite verificar o tipo do valor armazenado.

Também é possível alterar o tipo de valor armazenado em uma variável:

```javascript
var n1 = 10;
var n2 = 20;

n1 = "1" + 5;

console.log(n1 + n2);
```

Nesse exemplo, `n1` deixa de ser um número e passa a armazenar uma string.

---

## ➕ Operadores

Os operadores permitem realizar operações matemáticas, comparações e avaliações lógicas.

### Operadores aritméticos

```javascript
console.log(2 + 2);
console.log(2 - 2);
console.log(2 * 2);
console.log(8 / 4);
```

Principais operadores:

| Operador | Operação      |
| -------- | ------------- |
| `+`      | Adição        |
| `-`      | Subtração     |
| `*`      | Multiplicação |
| `/`      | Divisão       |

### Operadores de comparação

```javascript
console.log(2 == 2);
console.log(2 == 3);
```

O operador `==` compara os valores permitindo conversão de tipo.

Por exemplo:

```javascript
console.log(2 == "2");
```

O resultado é `true`, pois os valores são considerados equivalentes após a conversão.

### Igualdade estrita

O operador `===` compara **valor e tipo**:

```javascript
console.log(2 === "2");
```

Nesse caso, o resultado é `false`, pois um valor é `number` e o outro é `string`.

O operador `!==` funciona de maneira semelhante para verificar diferença estrita:

```javascript
console.log(3 !== "3");
```

### Operadores relacionais

```javascript
2 > 3
2 < 3
2 >= 2
2 <= 3
```

Eles permitem realizar comparações como:

* maior que: `>`
* menor que: `<`
* maior ou igual: `>=`
* menor ou igual: `<=`

---

## 📦 Arrays

Arrays são coleções utilizadas para armazenar vários valores em uma única estrutura.

Podem ser criados utilizando `[]` ou `new Array()`:

```javascript
var rhcp = ['Anthony', 'Chad', 'Flea'];
```

Apesar de armazenar uma coleção de valores, o `typeof` de um array retorna `object`:

```javascript
console.log(typeof rhcp);
```

### Adicionando elementos

O método `push()` adiciona um elemento ao final do array:

```javascript
rhcp.push('John');

console.log(rhcp);
```

### Removendo o último elemento

O método `pop()` remove o último elemento:

```javascript
rhcp.push('Josh');
rhcp.pop();

console.log(rhcp);
```

### Removendo o primeiro elemento

O método `shift()` remove o primeiro elemento:

```javascript
rhcp.shift();

console.log(rhcp);
```

### Encontrando a posição de um elemento

O método `indexOf()` retorna a posição de um elemento:

```javascript
var indice = rhcp.indexOf('Flea');

console.log(indice);
```

### Removendo elementos por posição

O método `splice()` pode ser utilizado para remover elementos a partir de determinada posição:

```javascript
var indice = rhcp.indexOf('Flea');

rhcp.splice(indice);

console.log(rhcp);
```

---

## 🔀 Estruturas condicionais

As estruturas condicionais permitem executar diferentes trechos de código de acordo com uma condição.

### `if`, `else if` e `else`

Exemplo utilizado no projeto:

```javascript
var idade = prompt("Qual sua idade?");

if (idade >= 18) {
    console.log("Sou maior de idade e posso ir sozinho no show do Iron Maiden!");
} else if (idade >= 12) {
    console.log("Sou menor de idade mas posso entrar acompanhado de um responsável no show do Iron Maiden.");
} else {
    console.log("Sou criança e ainda não posso ir a grandes shows.");
}
```

A estrutura avalia as condições em sequência:

1. Se a idade for maior ou igual a 18.
2. Caso contrário, verifica se é maior ou igual a 12.
3. Caso nenhuma condição seja verdadeira, executa o `else`.

### `switch`

O `switch` é utilizado quando existem diferentes possibilidades para um mesmo valor.

```javascript
var ingresso = prompt("Qual o tipo do ingresso?");

switch (ingresso) {
    case 'vip':
        console.log("Ficarei no camarote!");
        break;

    case 'premium':
        console.log("Ficarei na pista premium.");
        break;

    case 'comum':
        console.log("Ficarei na arquibancada.");
        break;

    default:
        console.log("Tipo de ingresso inválido....");
        break;
}
```

O `default` é executado quando nenhum dos `case` corresponde ao valor informado.

---

## ⚙️ Funções

Funções permitem encapsular um conjunto de instruções que pode ser executado quando necessário.

### Função sem retorno

```javascript
function welcome() {
    var welcome = "Hello Javascript - valor da função";

    document.getElementById("welcome").append(welcome);

    console.log(welcome);
}

welcome();
```

Nesse exemplo, a função executa uma ação, mas não retorna um valor para quem a chamou.

### Função com parâmetros

Funções podem receber valores através de parâmetros:

```javascript
function soma(n1, n2) {
    console.log(n1 + n2);
}

soma(15, 25);
```

### Função com retorno

Utilizando `return`, a função pode devolver um valor:

```javascript
function soma(n1, n2) {
    return n1 + n2;
}

console.log(soma(15, 25));
```

Isso permite utilizar o resultado da função em outras operações.

---

## 🔁 Laços de repetição

Laços de repetição permitem executar um determinado trecho de código várias vezes.

### `for`

O `for` utiliza uma declaração para controlar a repetição:

```javascript
for (var a = 0; a < 10; a++) {
    console.log(`Repetindo, porque ${a} é menor que 10.`);
}
```

O código é executado enquanto a condição `a < 10` for verdadeira.

### `while`

O `while` executa o código enquanto determinada condição for verdadeira:

```javascript
var i = 0;

while (i <= 10) {
    console.log(`Repetindo, porque ${i} é menor que 10.`);
    i++;
}
```

É importante alterar a variável utilizada na condição para evitar um loop infinito.

### `forEach`

O `forEach()` permite percorrer os elementos de um array:

```javascript
var rhcp = ['Anthony', 'Chad', 'Flea', 'John'];

rhcp.forEach(function(value, key) {
    console.log(`${value} na posição ${key}`);
});
```

Nesse exemplo:

* `value` representa o valor armazenado no array.
* `key` representa a posição do elemento.

---

## 🧱 Objetos

Objetos permitem agrupar informações relacionadas por meio de propriedades e comportamentos.

Um objeto pode conter valores e também funções.

### Objeto literal

```javascript
var album = {
    title: 'Californication',
    released: '1999',

    showInfo: function() {
        console.log(`Título do álbum: ${this.title}, lançado em ${this.released}`);
    }
};
```

As propriedades podem ser acessadas diretamente:

```javascript
console.log(album.title);
console.log(album.released);
```

E uma função armazenada como propriedade pode ser executada:

```javascript
album.showInfo();
```

O `this` permite acessar propriedades pertencentes ao próprio objeto.

### Criando um objeto com `new Object()`

Também é possível criar um objeto inicialmente vazio:

```javascript
var banda = new Object();

banda.nome = 'RHCP';
banda.origem = 'Califórnia';
```

Depois, propriedades e funções podem ser adicionadas:

```javascript
banda.showInfo = function() {
    console.log(`Nome da banda: ${this.nome}, origem ${this.origem}`);
};
```

O objeto também pode armazenar arrays:

```javascript
banda.integrantes = ['Anthony', 'Flea', 'Chad', 'John'];
```

E percorrer seus integrantes utilizando `forEach()`:

```javascript
banda.showIntegrantes = function() {
    this.integrantes.forEach(function(value, key) {
        console.log(value);
    });
};
```

---

## 🌐 DOM — Document Object Model

O **DOM (Document Object Model)** representa a estrutura HTML da página como uma árvore de elementos que pode ser acessada e manipulada pelo JavaScript.

Entre os elementos utilizados no projeto estão:

* `html`
* `h1`
* `p`
* `div`
* `input`
* `button`
* `form`
* `ul`
* `li`
* `a`
* `table`
* `tr`
* `td`

O JavaScript pode localizar elementos HTML através de métodos como:

```javascript
document.getElementById("welcome");
```

E alterar seu conteúdo:

```javascript
document.getElementById("welcome").append("Hello Javascript");
```

---

## 🧮 Exemplo prático: calculadora

O projeto possui uma calculadora simples utilizando HTML e JavaScript.

No HTML são definidos dois campos para entrada dos valores:

```html
<input type="text" id="numberOne" placeholder="Informe o valor 1">

<input type="text" id="numberTwo" placeholder="Informe o valor 2">

<button onclick="somarValores()">Somar valores</button>

<div id="resultado"></div>
```

Ao clicar no botão, a função `somarValores()` é executada.

```javascript
function somarValores() {
    var n1 = document.getElementById("numberOne").value;
    var n2 = document.getElementById("numberTwo").value;

    var result = parseInt(n1) + parseInt(n2);

    var divResultado = document.getElementById("resultado");

    divResultado.append("O resultado da soma é: " + result);
}
```

Nesse exemplo, o JavaScript:

1. Localiza o primeiro campo pelo `id`.
2. Obtém seu valor.
3. Localiza o segundo campo.
4. Obtém seu valor.
5. Converte os valores para inteiros utilizando `parseInt()`.
6. Realiza a soma.
7. Localiza a `div` de resultado.
8. Exibe o resultado na página.

---

## 🔗 Integração entre HTML e JavaScript

O JavaScript pode ser escrito diretamente dentro do HTML utilizando a tag `<script>`:

```html
<script type="text/javascript">
    console.log("Hello Javascript");
</script>
```

Também é possível utilizar um arquivo JavaScript externo:

```html
<script type="text/javascript" src="soma.js"></script>
```

Essa abordagem permite separar a estrutura da página HTML da lógica implementada em JavaScript.

---

## ▶️ Como executar

Este projeto utiliza JavaScript executado diretamente pelo navegador, portanto não é necessário um servidor ou processo de build para executar os exemplos básicos.

### 1. Clone ou baixe o projeto

```bash
git clone <URL_DO_REPOSITORIO>
```

### 2. Abra o arquivo `index.html`

O arquivo pode ser aberto diretamente no navegador.

### 3. Abra o DevTools

Para visualizar os resultados dos exemplos que utilizam `console.log()`:

* Abra o navegador.
* Pressione `F12`.
* Acesse a aba **Console**.

### 4. Teste a calculadora

Na página:

1. Informe o primeiro número.
2. Informe o segundo número.
3. Clique em **Somar valores**.
4. O resultado será apresentado na página.

---

## 🎯 Objetivo do projeto

O objetivo deste projeto é servir como material prático de estudo dos fundamentos do JavaScript, permitindo compreender conceitos essenciais antes de avançar para aplicações mais complexas.

Os exemplos também demonstram a interação entre **JavaScript, HTML e DOM**, mostrando como uma aplicação pode receber informações do usuário, processá-las e atualizar a página dinamicamente.

---

## 📝 Conceitos principais

Como resumo, os principais conceitos praticados são:

```text
JavaScript
│
├── Variáveis
│   └── Tipagem dinâmica
│
├── Operadores
│   ├── Aritméticos
│   ├── Comparação
│   └── Relacionais
│
├── Arrays
│   ├── push()
│   ├── pop()
│   ├── shift()
│   ├── indexOf()
│   └── splice()
│
├── Objetos
│   ├── Propriedades
│   ├── Métodos
│   └── this
│
├── Funções
│   ├── Parâmetros
│   └── return
│
├── Controle de fluxo
│   ├── if
│   ├── else if
│   ├── else
│   └── switch
│
├── Loops
│   ├── for
│   ├── while
│   └── forEach()
│
└── DOM
    ├── getElementById()
    ├── value
    └── append()
```

---

## 🚀 Próximos passos

Depois dos fundamentos apresentados neste projeto, alguns conceitos que podem ser estudados para evoluir o conhecimento em JavaScript são:

* `let` e `const`
* Arrow Functions
* Template Literals
* Métodos modernos de arrays (`map`, `filter`, `find`, `reduce`)
* Desestruturação
* Spread e Rest Operators
* Classes
* Módulos (`import` / `export`)
* Promises
* `async` / `await`
* Manipulação de eventos
* APIs e `fetch`
* Tratamento de exceções
* Node.js
* Testes automatizados com JavaScript
