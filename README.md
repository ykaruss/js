#JavaScript

* Multi-paradigma: com base em protótipo, funcional, imperativo e scripts  
* Criado: Brendan Eich  
* Estilo de tipagem: Dinâmica, fraca e implícita
* O núcleo do JavaScript pode ser estendido para uma variedade de propósitos, complementando assim a linguagem:
* O lado cliente do JavaScript fornece objetos para controlar um navegador web e seu Document Object Model (DOM). Por exemplo, as extensões do lado do cliente permitem que uma aplicação coloque elementos em um formulário HTML e responda a eventos do usuário, como cliques do mouse, entrada de formulário e de navegação da página.  
* O lado do servidor do JavaScript estende-se do núcleo  da linguagem, fornecendo objetos relevantes à execução do JavaScript em um servidor. Por exemplo, as extensões do lado do servidor permitem que uma aplicação comunica-se com um banco de dados, garantindo a continuidade de informações de uma chamada para a outra da aplicação, ou executar manipulações de arquivos em um servidor.  

#Referências
https://github.com/braziljs/eloquente-javascript  
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide

#Ferramentas
Firebug - https://addons.mozilla.org/pt-br/firefox/addon/firebug/  
Nodejs - https://nodejs.org/en/  

#Expressão e Afirmação
* Expressões podem ser encadeadas de forma semelhante às subfrases usadas na linguagem humana - uma subfrase pode conter sua própria subfrase, e assim por diante. Isto nos permite combinar expressões para expressar computações complexas arbitrariamente.
* Se uma expressão corresponde a um fragmento de sentença, uma afirmação, no JavaScript, corresponde a uma frase completa em linguagem humana. Um programa é simplesmente uma lista de afirmações.
* O tipo mais simples de afirmação é uma expressão com um ponto e vírgula depois dela.
```javascript
;
1;
!false;
```

#Ponto e vírgula
Em alguns casos, o JavaScript permite que você omita o ponto e vírgula no fim de uma declaração. Em outros casos ele deve estar lá ou coisas estranhas irão acontecer. As regras para quando ele pode ser seguramente omitido são um pouco complexas e propensas a erro.

#Palavras-chave e Palavras Reservadas
```javascript
break case catch continue debugger default delete do else false finally for function if implements in instanceof interface let new null package private protected public return static switch throw true try typeof var void while with yield this
```

#Variáveis
Não permite criar variáveis com nomes reservados  
Usa a palavra reservada var  
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
*Número  
*String  
*Booleans  
*Undefined  
*Objetos  
*Funções  

##Números  
```javascript
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number'; 
```
Infinity e -Infinity, que são usados para representar os infinitos positivo e negativo. O cálculo Infinity - 1 continua sendo Infinity, assim como qualquer outra variação dessa conta. Entretanto, não confie muito em cálculos baseados no valor infinito, pois esse valor não é matematicamente sólido, e rapidamente nos levará ao próximo número especial: NaN.
```javascript
typeof NaN === 'number';
typeof Number(1) === 'number'; 
```
NaN é a abreviação de “not a number” (não é um número), mesmo sabendo que ele é um valor do tipo número. Você receberá esse valor como resultado quando, por exemplo, tentar calcular 0 / 0 (zero dividido por zero), Infinity - Infinity ou, então, realizar quaisquer outras operações numéricas que não resultem em um número preciso e significativo.  
NaN é supostamente usado para indicar o resultado de alguma operação que não tenha sentido e, por isso, ele não será igual ao resultado de quaisquer outras operações sem sentido.  

##Strings
```javascript
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; 
typeof always return a string
typeof String("abc") === 'string'; 
but never use this form!
typeof String("This is the first line\nAnd this is the second") === 'string';
typeof String("con" + "cat" + "e" + "nate") === 'string';
```

##Booleans
```javascript
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; 
```
Valores Booleanos
```javascript
console.log(3 > 2)
console.log(3 < 2)
console.log("Aardvark" < "Zoroaster")
```
A forma na qual as strings são ordenadas é mais ou menos alfabética. Letras maiúsculas serão sempre “menores” que as minúsculas, portanto, “Z” < “a” é verdadeiro. Além disso, caracteres não alfabéticos (!, -, e assim por diante) também são incluídos nessa ordenação. A comparação de fato, é baseada no padrão Unicode, o JavaScript inicia da esquerda para a direita, comparando os códigos numéricos dos caracteres um por um.  
```javascript
console.log("Itchy" != "Scratchy")
console.log(NaN == NaN)
```

##Undefined  
```javascript
typeof undefined === 'undefined';
typeof blabla === 'undefined'; // an undefined variable
```

##Objetos  
```javascript
typeof {a:1} === 'object';
typeof [1, 2, 4] === 'object'; // use Array.isArray or Object.prototype.toString.call to differentiate regular objects from arrays
typeof new Date() === 'object';
```

##Funções
```javascript
typeof function(){} === 'function';
typeof Math.sin === 'function';
```

##Operadores Unários  
Todos os operadores que vimos operavam em dois valores, mas > typeof espera um único valor. Operadores que usam dois valores são chamados de operadores binários, enquanto que aqueles que recebem apenas um, são chamados de operadores unários. O operador - “negativo”pode ser usado tanto como binário quanto como unário.  
```javascript
console.log(- (10 - 2))
```
Nem todos os operadores são símbolos, sendo que alguns são escritos como palavras. Um exemplo é o operador > typeof, que produz um valor do tipo string contendo o nome do tipo do valor que você está verificando.  
```javascript
console.log(typeof 4.5)
console.log(typeof "x")
```
Existem também operadores que podem ser aplicados aos valores Booleanos. O JavaScript dá suporte a três operadores lógicos: and, or e not, que podem ser traduzidos para o português como e, ou e não. Eles podem ser usados para "pensar" de forma lógica sobre Booleanos.  
O operador && representa o valor lógico and ou, em português, e. Ele é um operador binário, e seu resultado é apenas verdadeiro se ambos os valores dados à ele forem verdadeiros.  
```javascript
console.log(true && false)
console.log(true && true)
```
O operador || indica o valor lógico or ou, em português, ou. Ele produz um valor verdadeiro se qualquer um dos valores dados à ele for verdadeiro.  
```javascript
console.log(false || true)
console.log(false || false)
```
Not, em português não, é escrito usando um ponto de exclamação (!). Ele é um operador unário que inverte o valor que é dado à ele. Por exemplo, !true produz false e !false produz true.  
```javascript
console.log(!0);
console.log(!5);
console.log(!"teste");
console.log("teste");
console.log(!!"teste");
```

##Prioridade de operadores   
Quando misturamos esses operadores Booleanos com operadores aritméticos e outros tipos de operadores, nem sempre é óbvio quando devemos usar ou não os parênteses.  
Na prática, você normalmente não terá problemas sabendo que, dos operadores que vimos até agora, || possui a menor precedência, depois vem o operador &&, em seguida vêm os operadores de comparação (>, ==, etc) e, por último, quaisquer outros operadores. Essa ordem foi escolhida de tal forma que, em expressões típicas como o exemplo a seguir, poucos parênteses são realmente necessários:  
```javascript
console.log(1 + 1 == 2 && 10 * 10 > 50);
```

##Operador ternário  
Ele é escrito usando um ponto de interrogação e dois pontos, como mostrado abaixo:  
```javascript
console.log(true ? 1 : 2);
console.log(false ? 1 : 2);
```
Esse operador é chamado de operador condicional (algumas vezes é chamado apenas de operador ternário, já que é o único operador desse tipo na linguagem). O valor presente à esquerda do ponto de interrogação “seleciona” qual dos outros dois valores será retornado. Quando ele for verdadeiro, o valor do meio é escolhido e, quando for falso, o valor à direita é retornado.  

##Valores Indefinidos  
Existem dois valores especiais, null e undefined, que são usados para indicar a ausência de um valor com significado. Eles são valores por si sós, mas não carregam nenhum tipo de informação.  
Muitas operações na linguagem que não produzem um valor com significado retornarão undefined simplesmente porque eles precisam retornar algum valor.  
A diferença de significado entre undefined e null é um acidente que foi criado no design do JavaScript, e não faz muita diferença na maioria das vezes. Nos casos em que você deve realmente se preocupar com esses valores, recomendo tratá-los como valores idênticos.  
Conversão Automática de Tipo  
JavaScript tentar fazer o seu melhor para aceitar quase todos os programas que você fornecer, inclusive aqueles que fazem coisas bem estranhas. Isso pode ser demonstrado com as seguintes expressões:  
```javascript
console.log(false == 0)
```
Quando um operador é aplicado a um tipo de valor “errado”, o JavaScript converterá, de forma silenciosa, esse valor para o tipo que ele desejar, usando uma série de regras que muitas vezes não é o que você deseja ou espera.  
Esse comportamento é chamado de coerção de tipo (ou conversão de tipo).  

##Conversão Automática de Tipo
```javascript
console.log(8 * null)
console.log("5" - 1)
console.log("5" + 1)
```
Na primeira expressão, null se torna 0 e, na segunda, a string "5" se torna o número 5. Já na terceira expressão, o operador + tenta efetuar uma concatenação de string antes de tentar executar a adição numérica e, por isso, o número 1 é convertido para a string "1".

##Conversão Automática de Tipo  
Quando algo que não pode ser mapeado como um número de forma óbvia (tais como "five" ou undefined) é convertido para um número, o valor NaN é produzido.  
Quaisquer outras operações aritméticas realizadas com NaN continuam produzindo NaN, portanto, quando você perceber que está recebendo esse valor em algum lugar inesperado, procure por conversões acidentais de tipo.  
```javascript
console.log("five" * 2)
```
Quando comparamos valores do mesmo tipo usando o operador ==, o resultado é fácil de se prever: você receberá verdadeiro quando ambos os valores forem o mesmo, exceto no caso de NaN.  
Por outro lado, quando os tipos forem diferentes, o JavaScript usa um conjunto de regras complicadas e confusas para determinar o que fazer, sendo que, na maioria dos casos, ele tenta apenas converter um dos valores para o mesmo tipo do outro valor. Entretanto, quando null ou undefined aparece em algum dos lados do operador, será produzido verdadeiro apenas se ambos os lados forem null ou undefined.  
```javascript
console.log(null == undefined);
console.log(null == 0);
```
O último exemplo é um comportamento que normalmente é bastante útil. Quando quiser testar se um valor possui um valor real ao invés de null ou undefined, você pode simplesmente compará-lo a null com o operador == (ou !=).  
Mas e se você quiser testar se algo se refere ao valor preciso false? As regras de conversão de strings e números para valores booleanos afirmam que 0, NaN e empty strings contam como false, enquanto todos os outros valores contam como true.  
Por causa disso, expressões como 0 == false e "" == false retornam true.  
Para casos assim, onde você não quer qualquer conversão automática de tipos acontecendo, existem dois tipos extras de operadores: === e !==.  
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

##Loops While e Do
console.log(0);  
console.log(2);  
console.log(4);  
console.log(6);  
console.log(8);  
console.log(10);  
console.log(12);  

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
