---
layout: post
date: 2016-08-22 11:52:30 -0300
title: Arrow Funcion

description: 'Como usa Arrow Functions e por que ele é lindo?'
tags:
- javascript
- es6
- javascript 2015
categories:
- Post
---

<img src="/images/bow-arrow.jpg" alt="Arrow" style="width: 100%;">

Antes de tudo, vale lembrar que o meu desafio, [Aprender todos os dias, durante 30 dias]({% post_url 2016-08-16-desafio-diario-1-let-var%}), já foi para saco logo no segundo dia, porque eu não consegui aprender nada e não queria tapar buraco com coisas que aprendi nos dias anteriores.

Mas eu vou falar sobre `Arrow Function` essa vez.

`Arrow Function` basicamente é algo muito lindo, que tem no `ES6`, que permite fazer as funções de uma forma mais curta, e mais algumas coisas.

Supondo que temos a função `square`, feito da seguinte forma:

```javascript
var square = function(num) {
	return num * num;
};
```

Poderia ser feito dessa forma em `Arrow Function`:

```javascript
var square = (num) => {
	return num * num;
};

var n1 = 2;
var n2 = square(n1);
```

> Mas só substituiu o `function` pelo `=>`?

Não, quando a função só tem uma linha, não são necessário os `{ }`:

```javascript
var square = (num) => return num * num;
```

> Hum, legal

E digo mais, quando a função só tem uma linha, não é necessário ter o `return`:

```javascript
var square = (num) => num * num;
```

E digo maaaiiis ainda, quando a função possui somente um parâmetro, os `( )` não são necessários:

```javascript
var square = num => num * num;
```

Comparando com a função inicial:

```javascript
// de
var square = (num) => {
	return num * num;
};

// para
var square = num => num * num;

// e então
var n1 = 2;
var n2 = square(n1);
```

> Interessante, mas quando preciso calcular `square`, `soma` ou coisas do tipo, ainda prefiro fazer `var n2 = n1 * n1` direto no código, e não em função separado.

A função `square` foi só um exemplo para facilitar a explicação do sintaxe do `Arrow Function`, vou mostrar como isso pode ficar mais interessante ainda.

Imagina uma situação, onde temos um array de objetos JSON, e queremos filtrar os objetos que tem `price` maior que `5.0`, depois pegar todos os `price` de todos objetos filtrados e aplicar um `parseFloat` para garantir que o formato do valor, para evitar problemas nos futuros manipulações:

```javascript
var products = [{
	description: "Mouse",
	price: "10.50"
}, {
	description: "Cup",
	price: "2.30"
}, {
	description: "Keyboard",
	price: "15.10"
}, {
	description: "Mouse 2",
	price: 11
}, {
	description: "Toddy",
	price: "8.60"
}];

// usando função normal
var p1 = products
	.filter(function(item) {
		return item.price > 5;
	})
	.map(function(item) {
		return parseFloat(item.price);
	});

// usando Arrow Function
var p2 = products
	.filter(item => item.price > 5)
	.map(item => parseFloat(item.price));

console.log(p1, p2);
```

Sim, a gente transformou um código de 7 linhas em 3, essa combinação de funções `map`, `reduce`, `filter` pode ser bastante comum nas manipulações de dados e pode diminuir bastante código usando `Arrow Function`, além de tornar o código mais legível.

Maaaasss, lembra daquele "e mais algumas coisas" que falei no começo?

O maior impacto que o `Arrow Function` fez é na questão de escopo (assim acredito), sabemos que quando cria uma função nova em `Javascript`, o escopo dentro dessa função será diferente do escopo de fora, por exemplo:

```javascript
function Product() {
	this.description;
	this.price;

	this.getIt = function() {
		setTimeout(function() {
			console.log(this);
			// vai imprimir objeto Window
			}, 500);
	};
}

var p = new Product();
p.getIt();
```

Executando o código de cima, pode reparar que o resultado não é o objeto `Product`, e sim `Window`, isso é causa da mudança do escopo, porem se usar `Arrow Function` nesse caso:

```javascript
function Product() {
	this.description;
	this.price;

	this.getIt = function() {
		setTimeout(() => {
			console.log(this);
			// Product
			}, 500);
	};
}

var p = new Product();
p.getIt();
```

Agora o valor imprimido é o `Product`, porque o `Arrow Function` não é atribuído um novo escopo. Isso pode eliminar muitos usos de `bind`, ou talvez pode gerar mais possibilidades na linguagem, isso é só o que eu acho.