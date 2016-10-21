#JavaScript

_Multi-paradigma:_ com base em protótipo, funcional, imperativo e scripts  
_Criado:_ Brendan Eich  
_Estilo de tipagem:_ Dinâmica, fraca e implícita 

O núcleo do JavaScript pode ser estendido para uma variedade de propósitos, complementando assim a linguagem:

_O lado cliente:_ Document Object Model (DOM).

_O lado do servidor:_ Nodejs.

#Referências
[Eloquente JavaScript](https://github.com/braziljs/eloquente-javascript)  
[Guia JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide)  
[NinjaJS](https://www.manning.com/books/secrets-of-the-javascript-ninja)  

#Ferramentas
[Firefox Developer Editor](https://www.mozilla.org/pt-BR/firefox/developer/)  
 [Firebug](https://addons.mozilla.org/pt-br/firefox/addon/firebug/)  
[Nodejs](https://nodejs.org/en/)  
[JSBIN](http://jsbin.com/?html,console,output)  

#Expressão e Afirmação
_expressão = sentença(...afirmação)**;**_
* O tipo mais simples de afirmação é uma expressão com um ponto e vírgula depois dela.
```javascript
;
1;
!false;
```

#[Palavras-chave e Palavras Reservadas](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference)

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
*Infinity e -Infinity, representam os infinitos positivo e negativo.*
```javascript
typeof NaN === 'number';
typeof Number(1) === 'number'; 
```
*NaN = “not a number” //(não é um número), mesmo sabendo que ele é um valor do tipo número. calcular 0 / 0 (zero dividido por zero), Infinity - Infinity;*

##Strings
```javascript
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; 
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
typeof [1, 2, 4] === 'object';
typeof new Date() === 'object';
```
[Em JavaScript, um array é um objeto que pode ser manipulado a partir de vários métodos.](https://developer.mozilla.org/pt-BR/docs/Glossario/array) 

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

##[Prioridade de operadores](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
```javascript
console.log(1 + 1 == 2 && 10 * 10 > 50);
```

##Operador ternário  
```javascript
console.log(true ? 1 : 2);
console.log(false ? 1 : 2);
```

##Valores Indefinidos  
**null**  
**undefined**
```javascript
console.log(null == undefined);
```

##Conversão Automática de Tipo  
```javascript
console.log(8 * null) // 0
typeof(8 * null) //"number"
console.log("5" - 1) // 4
console.log("5" + 1) //"51" 
console.log("five" * 2) //NaN
```
##[Operadores: === e !==](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Igualdade)
Retorna verdadeiro caso os operandos sejam iguais e do mesmo tipo.
Testa se o valor é precisamente igual (ou não) ao outro.  
É recomendo usar para prevenir inesperadas conversões de tipo que o farão tropeçar.  
Para null e undefined, não há problemas em usar os operadores curtos.  

##O Curto-Circuito de && e ||  
|| Se o parâmetro da esquerda for true, esse será retornado, senão retorna o parâmetro da direita.  
&& Se o parâmetro da esquerda for false, esse será retornado, senão retorna o parâmetro da direita.  
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
Vários operadores unários - para negativar um número, ! para negar uma lógica, e typeof para encontrar o tipo do valor.  

##Chamada de funções
Muitos dos valores fornecidos no ambiente padrão são do tipo _function_ (função). 
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
Uma linha do texto pode ser escrita dentro da janela de diálogo, que será retornada como uma string.  

##Fluxo de Controle
```javascript
var theNumber = Number(prompt("Escolha um numero!", ""));
alert("Seu numero ao quadrado é: " + Math.pow(theNumber,2));
```

##Execução Condicional
```javascript
var theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber))
 alert("Your number is the square root of " + Math.pow(theNumber,2));
```
```javascript
var theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber))
 alert("Your number is the square root of " + Math.pow(theNumber,2));
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
  (n % 3 == 0) ? output = "Pin" : output = n;
  console.log(output);
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
O papel da indentação é fazer a estrutura do código se destacar.  
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
  var x = "inside f1"; //var define o escopo de execução!
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

#Closure
```javascript
function multiplier(factor) {
  return function(number) {
    return number * factor;
  };
}
var twice = multiplier(2);//define uma variável cujo multiplicado é 2
var tri = multiplier(3);//define uma variável cujo multiplicado é 2
console.log(twice(5));//chama a variável para mutiplicar com 2
console.log(tri(5));//chama a variável para mutiplicar com 3
```
#Recursão
```javascript
function power(base, exponent) {
  if (exponent == 0)
    return 1;
  else
    return base * power(base, exponent - 1);
}
console.log(power(2, 3));
```
```javascript
function mul(a, b){ return b == 1 ? a : a+(mul(a, b - 1));}
console.log(mul(2, 8));
```
```javascript
 function fat(n){return n ? n*fat(n-1) : 1 };
```
#Memoização
```javascript
function isPrime(value){
	if(!isPrime.answers) isPrime.answers = {};
	if(isPrime.answers[value] != null) return isPrime.answers[value];
	
	var prime = value != 1;
	for(var i = 2; i<value;i++){
		if (value % i == 0){
			prime = false;
			break;
		}
	}
	return isPrime.answers[value] = prime;
}
console.log(isPrime(5), "5 is prime!");
console.log(isPrime.answers[5], "The answer was cached!");
```

#JavaScript HTML DOM

Quando uma página é carregada, o navegador cria um Document Object Modelo da página.  
JavaScript pode adicionar, alterar e remover todos os elementos e atributos HTML e estilos CSS na página.  
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
_window.document.element.property_ 

#Encontrar elementos HTML  
- document.getElementById( id ) - encontra um elemento pelo id
```html
<!DOCTYPE html>
<p id="intro">Hello World!</p>
<p>This example demonstrates the <b>getElementById</b> method!</p>
<p id="demo"></p>
<script>
var myElement = document.getElementById("intro");
document.getElementById("demo").innerHTML = 
"The text from the intro paragraph is " + myElement.innerHTML;
</script>
```
- document.getElementsByTagName( name ) - encontra um elemento pelo nome  
```html
<!DOCTYPE html>
<p>Hello World!</p>
<p>The DOM is very useful.</p>
<p>This example demonstrates the <b>getElementsByTagName</b> method</p>
<p id="demo"></p>
<script>
var x = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) is: ' + x[0].innerHTML;
</script>
```
- document.getElementsByClassName( name ) - encontra um elemento pela class
```html
<!DOCTYPE html>
<p>Hello World!</p>
<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>getElementsByClassName</b> method.</p>
<p id="demo"></p>
<script>
var x = document.getElementsByClassName("intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>
```
- document.querySelectorAll( "css" ) - encontra um elemento pela seletor css
```html
<!DOCTYPE html>
<p>Hello World!</p>
<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>querySelectorAll</b> method.</p>
<p id="demo"></p>
<script>
var x = document.querySelectorAll("p.intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>
```
#Mudando elementos HTML
- element.innerHTML = novo conteúdo - altera o html interno de um elemento  
- element.attribute = novo valor - altera o valor de uma atributo interno de um html  
- element.setAttribute (attribute, value) - altera o atributo de um elemento html  
- element.style.property = novo estilo - altera um estilo de um elemento html  

#Adicionar e eliminar Elements  
-  document.createElement( element ) - Cria um novo elemento
```html
<!DOCTYPE html>
<script>document.createElement("myHero")</script>
<style>
 myHero {
 	display: block;
      	background-color: red;
      	padding: 50px;
      	font-size: 30px;
 }  
</style>
<h1>A Heading</h1>
<myHero>My Hero Element</myHero>
```
- document.removeChild( element ) - Remove um elemento

```html
<!DOCTYPE html>
<ul id="myList"><li>Coffee</li><li>Tea</li><li>Milk</li></ul>
<p>Click the button to remove the first item from the list.</p>
<button onclick="myFunction()">Try it</button>
<script>
function myFunction() {
    var list = document.getElementById("myList");
    list.removeChild(list.childNodes[0]);
}
</script>
```
- document.appendChild( element ) - Adiciona um novo elemento
- document.replaceChild( element ) - Altera um elemento
- document.write( text ) - Escrever no fluxo de saída HTML

#Adicionando um Evento
```html
<!DOCTYPE html>
<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>
<script>
function mDown(obj) {
    obj.style.backgroundColor = "#1ec5e5";
    obj.innerHTML = "Release Me";
}
function mUp(obj) {
    obj.style.backgroundColor="#D94A38";
    obj.innerHTML="Thank You";
}
</script>
```
#Adicionando Eventos manipuladores  
[Exemplo](https://jsbin.com/yacagos/edit?html,js,output)
```html
<!DOCTYPE html>
<p>This example uses the addEventListener() method to add many events on the same button.</p>
<button id="myBtn">Try it</button>
<p id="demo"></p>
<script>
var x = document.getElementById("myBtn");
x.addEventListener("mouseover", myFunction);
x.addEventListener("click", mySecondFunction);
x.addEventListener("mouseout", myThirdFunction);
function myFunction() {
    document.getElementById("demo").innerHTML += "Moused over!<br>";
}
function mySecondFunction() {
    document.getElementById("demo").innerHTML += "Clicked!<br>";
}
function myThirdFunction() {
    document.getElementById("demo").innerHTML += "Moused out!<br>";
}
</script>
```
