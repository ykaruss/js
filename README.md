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
##Operadores: === e !==
Testa se o valor é precisamente igual (ou não) ao outro.  
É recomendo usar para prevenir inesperadas conversões de tipo que o farão tropeçar.  
Para null e undefined, não há problemas em usar os operadores curtos.  

##O Curto-Circuito de && e ||  
|| Se o parâmetro da esquerda for true, esse seré retornado, senão retorna o parâmetro da direita.  
&& Se o parâmetro da esquerda for false, esse seré retornado, senão retorna o parâmetro da direita.  
```javascript
console.log(null || "user")
console.log("Karl" || "user")
console.log(0 && true) 
console.log(" " && 1)
```

##Resumo
Alguns valores são criados digitando seu nome (true, null) ou valores (13, "abc").  
Eles podem ser combinados e transformados com operadores.  
Nós vimos operadores binários para aritmética (+, -, *, /, e %), um para concatenação de string (+), comparação (==, !=, ===, !==, <, >, <=, >=) e lógica (&&, ||).  
Vários operadores unários - para negativar um número, ! para negar uma lógica, e typeof para encontrar o tipo do valor).  

##Chamada de funções
Muitos dos valores fornecidos no ambiente padrão são do tipo function (função). 
Uma função é um pedaço de programa envolvido por um valor. 
```javascript
alert("Good morning!");
```

##Retornando Valores
Muitas funções são úteis por causa dos efeitos que elas produzem.  
Por exemplo, temos a função Math.max, que pega dois números e retorna o maior entre eles:  
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
O primeiro argumento é a questão.  
O segundo é o texto que o usuário inicia.  
Uma linha do texto pode ser escrita dentro da janela de diálogo. Retornar isso como uma string.  

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
```
```javascript
do {
 var name = prompt("Who are you?");
} while (!name);
console.log(name);
```
```javascript
var pin = Number(prompt("Qnts PIN?"));
for (var n = 1; n <= pin; n++) {
 var output = "";
if (n % 3 == 0)
 output += "Pin";
Console.log(output);
};
```
```javascript
for (var line = "#"; line.length < 8; line += "#")
console.log(line);
```
```javascript
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
O papel da indentação é que a estrutura do código se destaque.  
Em códigos complexos, onde temos blocos dentro de blocos, pode se tornar extremamente difícil distinguir onde um bloco começa e o outro termina.  
Com a indentação adequada, o formato visual do programa corresponde ao formato dos blocos contidos nele.  

##Quebrando a execução de um Loop
```javascript
for (var current = 20; ; current++) {
  if (current % 7 == 0) //o operador resto (%) é uma maneira fácil de testar se um número é divisível por outro.
    break;//quebra da iteração
}
console.log(current);
```
```javascript
for (i = 0; i < 10; i++) {
 if (i === 3) { continue; } //incrementa o iterador
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
return sem uma expressão após, irá retornar undefined.

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
```
```javascript
function power(base, exponent) {
  if (exponent == undefined) //tratamento de parâmetros
    exponent = 2;
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
}
console.log(power(4));
console.log(power(4, 3));
```
#JavaScript HTML DOM

Quando uma página é carregada, o navegador cria um Document Object Modelo da página.  
JavaScript pode adicionar, alterar e remover todos os elementos e atributos HTML na página.  
JavaScript pode mudar todos os estilos CSS na página.  
Métodos HTML DOM são ações que podem ser executadas (em Elementos HTML).  
No DOM, todos os elementos HTML são definidos como objetos.  
A interface de programação são as propriedades e métodos de cada objeto.  
A propriedade é um valor que você pode obter ou conjunto (como alterar o conteúdo de um elemento HTML).  
Um método é uma ação que você pode fazer (como adicionar ou excluir um elemento HTML).  
```html
<html>
 <body>
  <p id="demo"></p>
  <script>
   document.getElementById("demo").innerHTML = "Hello World!";
  </script>
 </body>
</html>
```
O objeto document representa a sua página web. getElementById é um método, enquanto InnerHTML é uma propriedade.  
regra geral = document.element.property  

#Encontrar elementos HTML  
- document.getElementById( id ) - acha um elemento pelo id  
- document.getElementsByTagName( name ) - acha uma elemento pelo nome  
- document.getElementsByClassName( name ) - acha uma elemento pela class  

#Mudando elementos HTML
- element.innerHTML = novo conteúdo - altera o html interno de um elemento  
- element.attribute = novo vamlor -  	altera o valor de uma atributo interno de um html  
- element.setAttribute (attribute, value) 	- altera o atributo de um elemento html  
- element.style.property = novo estilo - altera um estilo de um elemento html  

#Adicionar e eliminar Elements  
- document.createElement( element ) - Cria um novo elemento  
- document.removeChild( element ) -	Remove um elemento  
- document.appendChild( element ) -	Adiciona um novo elemento  
- document.replaceChild( element ) -	Altera um elemento    
- document.write( text ) 	- Escrever no fluxo de saída HTML  

#Adicionando Eventos manipuladores  
- document.getElementById( id ).onclick = function(){ code } 	- Adicionando código de manipulador de eventos para um evento onclick

#Encontrar objetos HTML
document.anchors - retorna todos os elementos <a> que tem um atributo nome  
document.baseURI	- retorna a URI  
document.body -	retorna o elemento <body>   	
document.cookie - retorna o cookie  
document.doctype - retorna o tipo de documentos  
document.documentElement -	retorna o  elemento <html>   	
document.documentMode - retorna o mode usado pelo navegador  
document.documentURI - retorna a  URI do documento  
document.domain	- retorna o nome do dominio do servidor do documento  
document.embeds -	retorna todos <embed> elementos  	
document.forms -	retorna todos <form> elementos 	
document.head -	retorna o <head> elemento 	
document.images -	retorna todos <img> elementos 	
document.implementation -	retorna o DOM implementação 	
document.inputEncoding -	retorna o documento encoding (character set) 	
document.lastModified -	retorna a data e tempo que o documento foi carregado   
document.links -	retorna todos <<area>> e <<a>> elementos que tem um atributo href  
document.readyState -	retorna o (loading) status do documento 	
document.referrer -	retorna o URI de referencia  	
document.scripts -	retorna todos <script> elementos 	
document.strictErrorChecking -	retorna if error checking is enforced 	
document.title -	retorna o <title> elemento 	
document.URL - retorna o completo URL do documento
