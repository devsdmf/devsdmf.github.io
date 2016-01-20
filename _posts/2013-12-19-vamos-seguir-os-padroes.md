---
layout: post
title: "Vamos seguir os padrões ?"
date: 2013-12-19 13:17:37
image: '/assets/img/'
description: 'Padrões são como regras, foram criados para serem seguidos, mas existem pessoas que insistem em quebrá-los.'
tags:
  - php
  - design patterns
  - psr
  - fig
  - frameworks
categories:
twitter_text: 'Padrões são como regras: foram criados para serem seguidos.'
---

Fala galera, tudo bem?!

Já faz algum tempo que venho amadurecendo a idéia de escrever um pouco sobre este assunto que é muito discutido mas pouco aplicado, estamos falando de padrões, mas não de padrões de projetos (Design Patterns) e sim de padrões de escrita e organização de código, em particularmente hoje, irei abordar sobre a PSR-FIG, que é um padrão de escrita e organização de código criado pela comunidade do PHP. Para os que adoram criticar e falar merdas asneiras a respeito do PHP por não ter padrões, não ter organização, ser muito gambiarrado mal escrito, bom, cale-se sente-se e leia o post até o fim.

**O que são Padrões de Codificação ?**

Padrões de Codificação ou Coding Patterns são uma série de regras documentadas por uma determinada comunidade para auxiliar e “padronizar” [ironic mode] a escrita do código para que toda contribuição que chegar na comunidade possa ser facilmente lida e até mesmo aprimorada por qualquer membro da comunidade, afinal essa é uma das permissas das licensas OpenSource, e não é uma das melhores coisas, toda vez que você for utilizar alguma biblioteca OpenSource ter de entender o padrão e a forma de escrita de código do criador da mesma, certo ? Então esse é um dos motivos de seguirem os Padrões de Codificação.

**Padrões de Codificação e o PHP?**

Como a maioria sabe e se você não sabe irá saber agora, o PHP tem a péssima fama (criada pelos próprios programadores e ~Java FanBoys~) de ser uma linguagem com código muito desorganizado, e de fato, até a chegada da Orientação à Objetos no PHP, ele era bem “chato” de se trabalhar por ser uma linguagem procedural e toda linguagem procedural acaba tendo um pouco de desorganização, sem excessão, então, o que fez a fama do PHP ser uma linguagem “suja” é por se tratar de uma linguagem bem antiga e muito aberta, e só depois de alguns anos ter implementado o conceito de Orientação à Objetos, mas nada impede de mudarmos essa fama, certo ? Para isso a comunidade PHP sentiu a necessidade de criar Padrões de Codificação, coisa que já vem com diversas linguagens novas, como o Java, então a comunidade se uniu e se esforçou e daí surgiu o FIG - Framework Interop Group.

**Um pouco de história - PHP FIG e a PSR.**

O PHP FIG - Framework Interop Group foi junção de representantes de vários “frameworks” desenvolvidos em PHP para que todos eles pudessem discutir sobre as semelhanças entre cada plataforma e encontrar uma forma de trabalhar juntos, dentre eles estão Cake PHP, Composer e Packagist, Doctrine ORM, Drupal, Joomla, Laravel, PEAR, phpBB, phpDocumentor, Symfony e até mesmo o Zend Framework, após alguns anos de discussão entre várias plataformas, alguém teve uma idéia: “Precisamos padronizar algumas coisas para que nossas plataformas possam ser integradas umas às outras sem dificuldade”, e daí começaram a discutir formas de se escrever o código e estruturar as plataformas de forma que todas pudessem trabalhar em conjunto facilmente e começaram a escrever o que chamamos hoje de PSR que são um conjunto de “regras” para a escrita e organização de código PHP, em outras palavras, Interoperabilidade.

**PSR e suas regras.**

A PSR atualmente possui 5 documentos, cada um tratando de regras específicas, sendo:

PSR-0: Autoloading Standard
PSR-1: Basic Coding Standard
PSR-2: Coding Style Guide
PSR-3: Logger Interface
PSR-4: Improved Autoloading
A PSR-0 trata especificamente de padrões para estrutura de Classes e Diretórios para que todas as ferramentas consigam trabalhar utilizando o mesmo AutoLoader, imagine-se utilizando o Zend Framework, Doctrine ORM e o Restler, todas essas ferramentas seguem os padrões da PSR-0 em sua estrutura de classes e diretórios, ou seja, você tem uma classe de AutoLoader que consegue trabalhar com 3 ferramentas distintas sem problemas.

A PSR-1 trata especificamente de padrões básicos para a escrita dos seus códigos, como tags, codificação, padrões de nomes de classes, padrões de nomes de métodos, entre diversas outras características estéticas do seu código, só que esse é um documento bem extenso com muitos detalhes, algumas regras dele dependem de outras, outras são opcionais, mas seguindo estes padrões facilita muito na hora da leitura de um código de terceiros, algo muito bem organizado e bem escrito, um código que dá gosto de ler.

A PSR-2 é uma extensão da PSR-1, todo este documento requer os padrões da PSR-1 implementados, neste documento estão padrões de formatação do seu código PHP, como espaços para indentação ao invés de tabs, máximo de caracteres por linha, ordem de declaração de namespaces, métodos, parâmetros e afins, abertura de chaves, chamadas à funções e métodos com multiplos parâmetros, não é um pré-requisito a implementação deste documento mas deixa a estética do código muito boa.

A PSR-3 é um documento que trata de padrões para logs do sistema, o foco deste documento não se resume tanto à código escrito no sistema e sim em leitura e análise de logs, seguindo determinado padrão, fica fácil identificar um problema no sistema e suas bibliotecas de terceiros, além de tudo, todas podem trabalhar utilizando o mesmo padrão de logs cada uma em seu arquivo ou até mesmo todas no mesmo arquivo.

A PSR-4 é o documento que trata de padrões de Autoloading trazem melhorias e melhor interoperabilidade para a PSR-0, sugerindo modificações nas classes de AutoLoader para que a mesma seja adaptável à estruturas que modificam alguns padrões da PSR-0.

**Comparação**

Abaixo estão algumas comparações entre códigos seguindo padrões PSR e códigos com padrões “próprios”:

AutoLoader usando PSR-0 (SliceLoader): [https://github.com/PHPSlice/Loader/blob/master/src/Slice/Loader.php](https://github.com/PHPSlice/Loader/blob/master/src/Slice/Loader.php)

AutoLoader com padrão próprio (Zend Framework 1.12): [https://github.com/zendframework/zf1/blob/master/library/Zend/Loader.php](https://github.com/zendframework/zf1/blob/master/library/Zend/Loader.php)

Classe utilizando PSR-1 e PSR-2 (SliceHttp): [https://github.com/PHPSlice/Http/blob/master/src/Slice/Http/ResponseAbstract.php](https://github.com/PHPSlice/Http/blob/master/src/Slice/Http/ResponseAbstract.php)

Classe sem padrão: [https://github.com/tropo/tropo-webapi-php/blob/master/tropo.class.php](https://github.com/tropo/tropo-webapi-php/blob/master/tropo.class.php)

**Conclusão**

As normas da PSR criadas pelo PHP FIG são apenas sugestões que ajudam e melhoram a organização e a interpretação de códigos PHP, seguindo estes padrões ganhamos em diversos quesitos, como compatibilidade, organização, fácil implementação e manutenção e um grande crescimento para a comunidade PHP e OpenSource, então, vamos seguir os padrões?
