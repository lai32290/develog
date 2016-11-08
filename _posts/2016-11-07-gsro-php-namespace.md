---
layout: post
date: 2016-11-07 21:53:00 -0300
title: GSRO - PHP Namespace

description: 'Namespace no PHP pra que?'
tags:
- php
- GSRO
- namespace
categories:
- Post
- GSRO
---

Esse é um post GSRO (Guia Super Rápido e Objetivo), então tentarei sei bem objetivo, e sem muitas enrolações.
 
## O que é namespace no PHP?
 
 `Namespace` no PHP é algo parecido com isso:
 <img src="/images/gsro-php-namespace.png" alt="PHP Namespace" style="width: 100%;">
 
## Pra que serve?
 
 Serve para evitar problemas quando tiver usando duas classes com mesmo nome, é meio parecido com `Sobrenome` na sala de aula,
 pode existir mais de uma pessoa que chama **João**, então na chamada, a professora não vai chamar só **João**, 
 mas pelo nome com o sobrenome, João Paulo, João do Santos, etc... pra ter certeza de qual esta chamando.
 
 A mesma coisa para código, ter o sobrenome para caso tenha duas classes com o mesmo nome.
 
## Como declarar?
 
 Namespace é sempre declarado fora de qualquer classe, como mostrado na imagem a cima.
 
```php

<?php
 namespace App\Http\Controllers;
 
 class GrsoController {
     // codigos da classe
 }
```

## Como chamar a classe com Namespace?

Para chamar a classe, deve chamar pelo nome completo

```php

<?php

$grso = new App\Http\Controllers\GrsoController();
```

Isso é muito trabalhoso pra ficar chamando toda hora, existe uma forma mais curta de fazer isso, 
que é esclarecendo a classe antes de usar, com a palavra `use`:

```php

<?php

use App\Http\Controllers\GrsoController;

$grso = new GrsoController();
$grso2 = new GrsoController();
$grso3 = new GrsoController();
$grso4 = new GrsoController();
// agora posso instanciar um milhão de objetos, sem repetir aquele nome grande
```

Mas e se mesmo somente o nome da classe já é grande, pode definir um `alias` (apelido) para ele, tipo chamar a 
**Carolina** de **Carol** ou chamar a irmã de **Tata**.

<img src="/images/mohammadpourkarkaragh.jpg" alt="Mohammadpourkarkaragh" />

```php
<?php

use App\Http\Controllers\GrsoController as Grso;

$grso = new Grso();
$grso2 = new Grso();
$grso3 = new Grso();
$grso4 = new Grso();
```