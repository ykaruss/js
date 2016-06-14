#JavaScript

* Multi-paradigma: com base em protótipo, funcional, imperativo e scripts  
* Criado: Brendan Eich  
* Estilo de tipagem: Dinâmica, fraca e implícita
* O núcleo do JavaScript pode ser estendido para uma variedade de propósitos, complementando assim a linguagem:
* O lado cliente: Document Object Model (DOM).
* O lado do servidor: Nodejs.

#Referências
Eloquente JavaScript - https://github.com/braziljs/eloquente-javascript  
Guia JavaScript - https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide  
NinjaJS -h ttps://www.manning.com/books/secrets-of-the-javascript-ninja  

#Ferramentas
Firefox Developer Editor - https://www.mozilla.org/pt-BR/firefox/developer/  
Firebug - https://addons.mozilla.org/pt-br/firefox/addon/firebug/  
Nodejs - https://nodejs.org/en/ 
JSBIN - http://jsbin.com/?html,console,output  

#Expressão e Afirmação
* expressão = sentença(...afirmação); <- Ponto e vírgula
* * O tipo mais simples de afirmação é uma expressão com um ponto e vírgula depois dela.
```javascript
;
1;
!false;
```

#Palavras-chave e Palavras Reservadas
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference

#Variáveis
Usa a palavra reservada var, Não permite nomes reservados.   
```javascript
var soma = 5+5;
console.log(soma);
soma+=++soma;
console.log(soma);
```
#Ambiente
A coleção de variáveis e seus valores que existem em um determinado tempo é chamado de environment (ambiente).  
Quando um programa inicia, o ambiente não está vazio. Ele irá conter no mínimo o número de variáveis que fazem parte do padrão da linguagem. E na maioria das vezes haverá um conjunto adicional de variáveis que fornecem maneiras de interagir com o sistema envolvido.  
Por exemplo, em um navegador, existem variáveis que apontam para funcionalidades que permitem a você inspecionar e influenciar no atual carregamento do website, e ler a entrada do mouse e teclado da pessoa que está usando o navegador.

#Valores, Tipos e Operadores  
Existem seis tipos básicos de valores no JavaScript:  
- Número  
- String  
- Booleans  
- Undefined  
- Objetos  
- Funções  

##Números  
```javascript
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number'; 
```
Infinity e -Infinity, representam os infinitos positivo e negativo. 
```javascript
typeof NaN === 'number';
typeof Number(1) === 'number'; 
```
NaN = “not a number” //(não é um número), mesmo sabendo que ele é um valor do tipo número. calcular 0 / 0 (zero dividido por zero), Infinity - Infinity;

##Strings
```javascript
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; 
typeof always return a string
typeof String("abc") === 'string'; 
typeof String("This is the first line\nAnd this is the second") === 'string';
typeof String("con" + "cat" + "e" + "nate") === 'string';
```

##Booleans
```javascript
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; 
```

##Valores Booleanos  
```javascript
console.log(3 > 2)
console.log(3 < 2)
console.log("Aardvark" < "Zoroaster")
console.log("Itchy" != "Scratchy")
console.log(NaN == NaN)
```

##Undefined  
```javascript
typeof undefined === 'undefined';
typeof blabla === 'undefined';
```

##Objetos  
```javascript
typeof {a:1} === 'object';
typeof [1, 2, 4] === 'object'; //https://developer.mozilla.org/pt-BR/docs/Glossario/array
typeof new Date() === 'object';
```

##Funções
```javascript
typeof function(){} === 'function';
typeof Math.sin === 'function';
```

##Operadores Unários  
```javascript
console.log(-(10 - 2));
console.log(typeof 4.5)
console.log(typeof "x")
```

##Operadores lógicos  
```javascript
console.log(true && false)
console.log(true && true)
console.log(false || true)
console.log(false || false)
console.log(!0);
console.log(!5);
console.log(!"teste");
console.log("teste");
console.log(!!"teste");
```

##Prioridade de operadores   
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Operator_Precedence
```javascript
console.log(1 + 1 == 2 && 10 * 10 > 50);
```

##Operador ternário  
Ele é escrito usando um ponto de interrogação e dois pontos, como mostrado abaixo:  
```javascript
console.log(true ? 1 : 2);
console.log(false ? 1 : 2);
```

##Valores Indefinidos  
- null  
- undefined  
```javascript
console.log(null == undefined);
```

##Conversão Automática de Tipo  
```javascript
console.log(8 * null) // 0
console.log("5" - 1) // 4
console.log("5" + 1) //51 
console.log("five" * 2) //NaN
```
##Operadores: === e !==.  ---PAREI AQUI--
O primeiro teste se o valor é precisamente igual ao outro, e o segundo testa se ele não é precisamente igual. Então "" === false é falso como esperado.  
É recomendo usar os operadores de comparação de três caracteres defensivamente, para prevenir inesperadas conversões de tipo que o farão tropeçar.  
Mas quando você tem certeza de que os tipos de ambos os lados serão iguais, ou que eles vão ser ambos null/undefined, não há problemas em usar os operadores curtos.  

##O Curto-Circuito de && e ||  
Os operadores lógicos && e || tem uma maneira peculiar de lidar com valores de tipos diferentes. Eles vão converter o valor à sua esquerda para o tipo booleano a fim de decidir o que fazer, mas então, dependendo do operador e do resultado da conversão, eles ou retornam o valor à esquerda original, ou o valor à direita.  
O operador || vai retornar o valor à sua esquerda quando ele puder ser convertido em true, ou valor à sua direita caso contrário. Ele faz a coisa certa para valores booleanos, e vai fazer algo análogo para valores de outros tipos. Isso é muito útil, pois permite que o operador seja usado para voltar um determinado valor predefinido.  
```javascript
console.log(null || "user")
console.log("Karl" || "user")
```
O operador && trabalha similarmente, mas ao contrário. Quando o valor à sua esquerda é algo que se torne false, ele retorna o valor, e caso contrário ele retorna o valor à sua direita.  
Outro importante propriedade destes 2 operadores é que a expressão a sua direita é avaliada somente quando necessário. No caso de true || X, não importa o que X é pode ser uma expressão que faça algo terrível o resultado vai ser verdadeiro, e X nunca é avaliado. O mesmo acontece para false && X, que é falso, e vai ignorar X.  

##Resumo
Alguns valores são criados digitando seu nome (true, null) ou valores (13, "abc").  
Eles podem ser combinados e transformados com operadores. Nós vimos operadores binários para aritmética (+, -, *, /, e %), um para concatenação de string (+), comparação (==, !=, ===, !==, <, >, <=, >=) e lógica (&&, ||), como também vários operadores unários - para negativar um número, ! para negar uma lógica, e typeof para encontrar o tipo do valor).  
Isto lhe dá informação suficiente para usar o JavaScript como uma calculadora de bolso, mas não muito mais.  

##Chamada de funções
Muitos dos valores fornecidos no ambiente padrão são do tipo function (função). 
Uma função é um pedaço de programa envolvido por um valor. 
```javascript
alert("Good morning!");
```

##Retornando Valores
Muitas funções são úteis por causa dos efeitos que elas produzem. 
É também possível para uma função produzir um valor, no caso de não ser necessário um efeito colateral. Por exemplo, temos a função Math.max, que pega dois números e retorna o maior entre eles:
```javascript
console.log(Math.min(2, 4) + 100);
```

##prompt e confirm
```javascript
confirm("é verdade?");
```
Retorn um true caso OK ou false caso Cancel
```javascript
prompt(“Qual o seu nome?”, “Entre com seu nome aqui!!!”); 
```
prompt pode ser usado para criar uma questão "aberta". O primeiro argumento é a questão; o segundo é o texto que o usuário inicia. Uma linha do texto pode ser escrita dentro da janela de diálogo, e a função vai retornar isso como uma string.

##Fluxo de Controle
```javascript
var theNumber = Number(prompt("Escolha um numero!", ""));
alert("Seu numero ao quadrado é: " + theNumber * theNumber);
```

##Execução Condicional
```javascript
var theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber))
 alert("Your number is the square root of " + theNumber * theNumber);
```

##Execução Condicional
```javascript
var theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber))
 alert("Your number is the square root of " + theNumber * theNumber);
else
 alert("Hey. Why didn't you give me a number?");
```
```javascript
var num = Number(prompt("Pick a number", "0"));
if (num < 10)
alert("Small");
else if (num < 100)
alert("Medium");
else
alert("Large");
```

##Loops While, Do While, for
```javascript
var number = 0;
while (number <= 12) {
 console.log(number);
 number += 2;
}

do {
var name = prompt("Who are you?");
} while (!name);
console.log(name);

var pin = Number(prompt("Qnts PIN?"));
for (var n = 1; n <= pin; n++) {
var output = "";
if (n % 3 == 0)
output += "Pin";
Console.log(output);
};

for (var line = "#"; line.length < 8; line += "#")
console.log(line);

var size = 8, board = "";
for (var y = 0; y < size; y++) {
  for (var x = 0; x < size; x++) {
    if ((x + y) % 2 == 0)
      board += " ";
    else
      board += "#";
  }
  board += "\n";
}
console.log(board);
```

##Indentando Código
O papel da indentação dentro dos blocos é fazer com que a estrutura do código se destaque. Em códigos complexos, onde temos blocos dentro de blocos, pode se tornar extremamente difícil distinguir onde um bloco começa e o outro termina.  
Com a indentação adequada, o formato visual do programa corresponde ao formato dos blocos contidos nele.  

##Quebrando a execução de um Loop
Ter uma condição que produza um resultado false não é a única maneira que um loop pode parar. Existe uma declaração especial chamada break que tem o efeito de parar a execução e sair do loop em questão.
```javascript
for (var current = 20; ; current++) {
  if (current % 7 == 0)
    break;
}
console.log(current);
```
Usar o operador resto (%) é uma maneira fácil de testar se um número é divisível por outro. Se for, o resto da divisão entre eles é zero.

A palavra-chave continue é similar ao break, de modo que também influencia o progresso de um loop. Quando continue é encontrado no corpo de um loop, o controle de execução pula para fora do corpo e continua executando a próxima iteração do loop.
```javascript
for (i = 0; i < 10; i++) {
 if (i === 3) { continue; }
 console.log(i);
}
```

##Resolvendo um valor com switch
```javascript
switch (prompt("What is the weather like?")) {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}
```

##Comentários
// linha  
/* e 
bloco */ 

##Função
```javascript
var square = function(x) {
  return Math.pow(x,2)
};
square(2);

var makeNoise = function() {
  console.log("Pling!");
};
makeNoise();

var power = function(base, exponent) {
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
};
console.log(power(2, 10));
```
A palavra-chave return sem uma expressão após, irá fazer com que o retorno da função seja undefined.

##Parâmetros e Escopos

Os parâmetros de uma função comportam-se como variáveis regulares. Seu valor inicial é informado por quem invocou a função e não pelo código da função em si.

Uma propriedade importante das funções é que variáveis definidas dentro do "corpo" delas, incluindo seus parâmetros, são locais à própria função. Isso significa, por exemplo, que a variável result no exemplo power será criada novamente toda vez que a função for invocada, sendo que as diferentes execuções não interferem umas nas outras.

Essa característica de localidade das variáveis se aplica somente aos parâmetros e às variáveis que forem declaradas usando a palavra-chave var dentro do "corpo" de uma função. Variáveis declaradas fora do contexto de alguma função são chamadas de globais (não locais), pois elas são visíveis em qualquer parte da aplicação. É possível acessar variáveis globais dentro de qualquer função, contanto que você não tenha declarado uma variável local com o mesmo nome.
```javascript
var x = "outside";
var f1 = function() {
  var x = "inside f1";
};
f1();
console.log(x);

var f2 = function() {
  x = "inside f2";
};
f2();
console.log(x);

function power(base, exponent) {
  if (exponent == undefined)
    exponent = 2;
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
}
console.log(power(4));
console.log(power(4, 3));
```
callback

