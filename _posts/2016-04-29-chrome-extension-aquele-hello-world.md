---
layout: post
title: "Chrome Extension - Aquele Hello World"
date: 2016-04-29 22:23:00
image: '/assets/img/'
description: 'Um pequeno introdução sobre chrome Extension'
tags:
- javascript
- chrome-extension
categories:
- Post
---

Sou uma criança que sempre gostou de jogos, principalmente aqueles jogos web feito em HTML (também gostava dos Flash, mas o negócio era outra), apesar que só tinha internet discada... pi pi pi pi...... mas gostava muito de jogos feito em HTML, pois não precisam instalar, salva automaticamente, são leves, e são online né! Para aquela época, poxa vida, gráfico pra quê?

Em uma dessas pesquisas de "como ficar forte" em tal jogo, acabei conhecendo uns caminhos "alternativos", tais como Greasemonkey, mesmo que eu não sabia programar, mas sempre achei isso incrível, até que hoje estou aqui programando, e resolvi fazer plugin para facilitar uns processos na minha vida de trabalho de programador web no dia-a-dia, aproveitando que as extensões do Chrome já estão bem maduros (migrei do Firefox para Chrome, viu só?), então comecei a estudar sobre o desenvolvimento de **Chrome Extension**, e falando um pouco sobre essa tal de **Greasemonkey** e **Chrome Extension**.

### Greasemonkey ou Tampermonkey

Greasemonkey e Tampermonkey são plugins do browser, feitos para gerenciamento de Userscripts.

Na verdade eu nunca estudei sobre O QUE É USERSCRIPT, desde quando eu comecei a mexer com ele, já fui direto no [Greasemonkey](https://addons.mozilla.org/pt-br/firefox/addon/greasemonkey/), depois no [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo), quando migrei do Firefox para Chrome.

Mas Userscript, basicamente é um script que serve para adicionar ou alterar alguma ação da página, como adicionar alguma função para um botão, além da ação padrão.

É possível fazer algo bem incrível com ele, ~~principalmente para fazer umas automações de jogos web em HTML~~ (meu passado me condena), mas como não é o foco para este post, não vou prolongar demais no assunto, comente comentarei sobre uns prós e contras, para mostrar um pouco de quais situações compensa mais usar Userscript ou Chrome Extension.

Falarei baseando em Greasemonkey e Tampermonkey, que são os dois gerenciadores que já usei, mas acredito que para os outros plugins do mesmo gênero, as características provavelmente serão as mesmas.

#### Prós

Caso necessita fazer adicionar alguma ação pequena e simples ou fazer pequenos ajustes na página, como esconder blocos de propagandas chatas da página que acessa sempre.

Para esses tipos de coisas rápidas, realmente é bem (apesar que existe uns scripts na internet, que faz umas alterações cabulosas no site), pois com apenas alguns cliques no painel, já pode começar a codar para o que interessa, e todo o código será injetado quando a página alvo for carregada.

#### Contra

A parte chata é, que todo código fica em um único documento ou arquivo se preferir, que são armazenados em um local específico misterioso (a verdade é que eu pesquisei, mas não aprofundei sobre essa questão para poder falar com tanta afirmação), os códigos são salvos em um tipo de database dele que não tem acesso fácil para o usuário (nós, desenvolvedores de script), até onde eu sei.

Como os códigos são salvos nesse local misterioso que não tem acesso fácil, consequentemente, não é possível codificar pelo seu editor preferido, deve escrever todo o código no editor padrão incluso no gerenciador (desconsiderando que existe algumas maneiras que permitem codificar no editor preferido em fase de DESENVOLVIMENTO). Mesmo que com o tempo, o editor padrão foram aperfeiçoando, mas nada igual ao seu editor preferido, lindo, poderoso e cheio de flu flu né.

Quando tiver necessidade de inserir HTML complexo na página, é muito trabalhoso, pois todo HTML deve ser feito em string concatenado para ser adicionado na página em momento certo.

Para compartilhar o script com alguém que não tem plugin de Userscript instalado ou mesmo aqueles usuário que mal sabem sobre plugins para browser, dá impressão que precisa instalar dois PROGRAMAS para realizar uma função simples, dependendo do caso.

### Chrome Extension

O Chrome Extension nada mais que é o plugin para Chrome, a mesma coisa do plugin do **Firefox**, são feitos em Javascript (na verdade não sei como é feito plugin do Firefox, mas acredito que seja em Javascript também), permite criar, adicionar funcionalidades poderosas à página, igual no Userscript.

O legal do Chrome Extension é que de tão evoluído que o Chrome está hoje, além de criar extensões, é possível até criar aplicações desktop em multiplataforma (Windows, Linux e Mac) usando HTML, CSS e Javascript, mesmo que também existe outras coisas para isso, tipo [Electron](http://electron.atom.io/), [Node Webkit](http://nwjs.io/) entre outras.

E claro, como o assunto é **Chrome Extension** e não **Chrome App**, vou falar sobre umas vantagens e desvantagens dele.

#### Prós

A maior vantagem que eu senti, migrando do Userscript para Chrome Extension, é que com Chrome Extension pode criar o "projeto" (no caso, a extensão) em vários arquivos separados, como se fosse criando sites normais mesmo, criando arquivo HTML, incluindo arquivos JS e CSS com tags, sem ter que criar toda a estrutura HTML em string para ser concatenado (Autocompletes de HTML, JS, CSS; snippets e todas aquelas coisas maravilhosas do meu editor favorito entrando na cabeça), consequentemente, o código fica muito organizado e fácil de manter.

E como é algo feito para o próprio navegador, também é possível fazer comunicações de informações entre as abas, caso necessário (apesar que eu não vejo o porquê de fazer isso, foi só um exemplo mesmo).

Também com as atualizações do Chrome, é possível permitir que crie uma extensão para site de cambio e ficar atualizando página em cada certo tempo, analisando quanto está o dólar, caso tiver abaixo de um certo valor, criar uma notificação para informar o usuário. Eu fiz isso um tempo atrás, usando Userscript e avisando usuário com simples **alert();**, também é bem simples, mas isso é so para mostrar a possibilidade de usar notificações.

Para o desenvolvimento do Chrome Extension, que seria praticamente a criação de um mini projeto, pode criar ele como se fosse qualquer outro projeto web, separando códigos em arquivos, arquivos em pastas e codando em qualquer editor preferido que quiser.

Caso tiver feito alguma extensão que ficou muito legal, e quiser compartilhar com o mundo, também pode publicar o plugin na própria loja de extensão do Chrome, onde os usuários consigam realizar uma instalação muito rápida e fácil para usá-lo.

#### Contra

Tem vários pontos positivos, e claro que não existe algo perfeito no mundo (ou muito poucos).

Comparando com Userscripts, caso precisar criar algo pequeno e rápido, como simplesmente mudar botão para alguma posição preferida, adicionar algum CSS para melhorar um pouco o layout e usabilidade (Eu fazia isso com lista de tarefas, destacando as tarefas com meu nome), para esses casos, ou outros do tipo, talvez seria realmente mais fácil usar o Userscript, no qual com alguns cliques e umas linhas de código já matava o problema, não é necessário criar arquivos padrões do Chrome Extension.

E como é algo com possibilidades mais amplos, consequentemente requer uma curva de aprendizagem maior, mas como são todos programadores, nada que um pouco de [docs](https://developer.chrome.com/extensions) não resolva.

### Conclusão

Eu resolvi escrever sobre esse assunto, pois é algo que estou estudando recentemente, não é porque eu manjo, então pode ser também que escrevi só abobrinhas, mas, vivendo e aprendendo, errando e melhorando.

Pretendo com calma, escrever uma série sobre desenvolvimento de Chrome Extension, com as coisas que vou estudando e aprendendo, servindo para mim como anotações e compartilhando com pessoas com mesmo interesse, e tamos ai!