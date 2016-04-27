---
layout: post
title: "Hello Jekyll World"
date: 2016-04-26 06:10:00
image: '/assets/img/'
description: 'Hello Jekyll World! Finalmente aqui estou!'
tags:
- jekyll
- github
- hello-world
categories:
- Post
---

Depois de muitas tentativas e enrolações, finalmente aqui está esse tal de blog.

Essa é a minha primeira experiencia em criar blog, e esse é o meu primeiro post, sou extrangeiro, escrevo mal, pode acontecer de escrever errado (e podem rir, hehehe), mas quero escrever algo para registar os meus estudos, problemas e também compartilhar para todos das coias que eu gosto.

Então vamos ao que interessa! Como este blog foi feito em [Jekyll](https://jekyllrb.com/), então vou falar sobre como criar o blog em Jekyll e hospedar no [Github](https://github.com), usando [template](https://github.com/willianjusten/will-jekyll-template) que o [Willian Justin](https://twitter.com/Willian_justen) criou, que também foi quem me ajudou a subir este blog.

O processo é bem simplte, apesar que tive algumas dificuldades, acredito que demoraria muito mais se não tivesse ajuda do Willian.



### O que é Jekyll?

Resumidamente, o Jekyll é um gerador, no qual é possivel criar template de site e posts separadamente, deixando que o Jekyll faz combinação do template e posts automaticamente e gerando paginas em HTML puro, sem precisar de banco de dados, Java, PHP, C# ou qualquer outra coisa!

E com o nosso grande Github, é possivel até de ficar sem gasto nem com hospedagem e nem com dominio (ganhei $2.00 por falar isso heim, mentira)

### Passo 1 - Conta Github

Como o blog será hospedado em Github, então primeiro de tudo é ter uma conta no Github, eu acredito que a maioria dos desenvolvedores já devem ter a sua conta, e se não tiver, não tem muito segredo, é so entrar no site e cadastrar.


### Passo 2 - Fork

Depois que estar com a conta do Github logado, so precisa fazer um fork do [repositorio](https://github.com/willianjusten/will-jekyll-template) do template no qual vamos usar.

![Fork](images/hello-jekyll-world-fork.png)

### Passo 3 - Renomear Repositório

Para que o Github cria o dominio e hospeda o seu site, o nome do repositório precisa seguir a regra definida, que é o **seuUserName.github.io**.

Supondo que o meu username do Github é **lai32290**, o nome do repositório terá que ser chamado **lai32290.github.io**.

Existe alguma outra forma para que funcione mesmo deixando algum outro nome qualquer, porêm como não é o caso.

Após renomear o repositório corretamente, precisa esperar um tempinho para que o Github cria o dominio, e já pode começar tentar acessar a URL com o nome do repositório, no meu caso: **lai32290.github.io**, caso aparecer o blog, mesmo com layout quebrado, significa que está funcionando.


### Passo 4 - Clone

Agora que tem o template no seu repositório, é necessário baixar o projeto no computador para facilitar para configuração.

{% highlight shell %}
git clone <seu repositorio do template>
{% endhighlight %}


### Passo 5 - Configurando blog

Como a intensão é hospedar no Github e usar o dominio do Github também, é preciso que faz algumas configurações no arquivo **_config.yml**, retirando valor das propriedades seguintes:

{% highlight yml %}
baseurl: "" # the subpath of your site, e.g. /blog
url: "" # the base hostname & protocol for your site e.g. http://willianjusten.com.br
{% endhighlight %}

E foi aqui mesmo que eu errei, na verdade não lembro exatamente qual configuração eu testei, mas sai atirando para todas as possibilidades, e no fim de tudo, descobri que nada funcionava, simplesmente por causa do cache do navegador!! (Oh god why!?), então caso for testar configuração, garanta que o resultado NÃO SEJA do cache.

Além de alterar essas duas propriedades, também pode preencher as outras da sua maneira.


### Passo 6 - Commitando configuração

Depois que ter o arquivo **_config.yml** configurado, salve e mande de volta para o Github:

{% highlight shell %}
git add .
git commit -m 'ajustando config'
git push -u origin master
{% endhighlight %}


### Passo 7 - Pronto!

Após realizar o commit e push das configurações para o Github, tente novamente entrar na URL, e tera o layout arrumado e bonitinho, agora é so criar posts e atualizar o seu blog.


### Curso

Como esté post estou falando sobre Jekyll e do template criado pelo Willian, não tem porque eu não falar do curso gratuito que o Willian fez, ensinando Jekyll desde o que é Jekyll, até mesmo hospedar no Github e muitas outras dicas e conceitos.

E também foi nesse curso que aprendi a usar um pouco de Jekyll (afinal, so usando mesmo para saber se realmente aprendeu né), e retomando coragem para aventurar novamente em Jekyll.

Recomendo que os iniciante e interessados façam o curso, que não é um curso longo nem cansativo

[Curso Jekyll do Willian Justen (Its free!!)](http://willianjusten.teachable.com/courses/criando-sites-estaticos-com-jekyll)


### Conclusão

E essa é a conclusão do meu primeiro post, do meu primei blog! Espero que consigo caminhar bastante com esse blog!