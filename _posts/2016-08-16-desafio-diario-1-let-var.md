---
layout: post
date: 2016-08-16 11:23:04 -0300
title: Desafio Diário - Aprender Todos os Dias (Dia 1)

description: 'Desafio diário - let vs var'
tags:
- desafio-diario
categories:
- Post
---

![Desafio](/images/desafio.jpg)

### Introdução

Sempre escuto falando que uma das melhores forma de aprender coisas novas é compartilhando as coisas que aprendeu, reforçando a ideia na cabeça dessa maneira.

Como eu sempre tento anotar tudo que estou aprendendo, mas nem sempre consigo, resolvi criar um desafio para eu mesmo.

O desafio basicamente é aprender pelo menos uma coisa por dia, durante 30 dias, independente se é uma coisa mais complexo ou algo mais simples, pois acredito que todos conhecimentos vem da junção de pequenos conhecimentos, e estarei registrando minhas aprendizagens aqui para servir de anotação e tentar compartilhar com quem precisa, mesmo que o post pode ficar meio pequeno, mas o importante é o conteúdo.

Pronto, chega de filosofar.

### Aprendizagem

Assunto: `Javascript`

Agora em `Javascript`, temos variáveis além do tipo `var` e `const`, temos o tipo `let`.

A diferença do `let`e do `var` basicamente está no escopo (ou só no escopo), onde `var` considera a função como escopo, e o `let` considera o bloco de código como escopo.

Com exemplo pode explicar melhor:

```javascript
function printIterar() {
    for(var i = 0; i < 10; i++) {
        console.log('Dentro do for', i);
    }

    console.log('Fora do for', i); // Fora do for 10
}

printIterar();
```

Se executar esse código, podem ver que o variável `i` imprimido no "Fora do for" será 10, isso é porque ele foi declarado do tipo `var`, então ele considera a função `printIterar` como escopo, em outras palavras, o variável pode ser acessado dentro da função toda.

```javascript
function printIterar() {
    for(let i = 0; i < 10; i++) {
        console.log('Dentro do for', i);
    }

    console.log('Fora do for', i); // Fora do for 10
}

printIterar();
```

Agora, trocando o variável do tipo `var` para `let` e tentar executar o código, isso pode ocorrer um erro, reclamando que o variável `i` não foi definido.

Isso é porque variáveis do tipo `let` consideram o bloco atual como escopo, no caso é o bloco dentro do `for`, em outras palavras, ele só pode ser acessado dentro do bloco que foi definido, se variável foi definido dentro do `if`, somente pode ser acessado dentro desse `if`.