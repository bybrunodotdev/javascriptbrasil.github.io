---
layout: page
title: Sobre
permalink: /sobre/
published: true
---

<div class="page" markdown="1">

{% capture page_subtitle %}
<img
    class="me"
    alt="{{ author.name }}"
    src="{{ site.author.photo | relative_url }}"
    srcset="{{ site.author.photo2x | relative_url }} 2x"
/>
{% endcapture %}

{% include page/title.html title=page.title subtitle=page_subtitle %}

## Quem faz parte do projeto?
Todos que fizerem uma contribuição no GitHub e todos que acessam esse site, ou seja, você faz parte de tudo isso também.

## Aceitam doação?
No momento, optamos por não receber nenhum tipo de ajuda financeira por não existir gastos significantes por de trás do projeto. Dessa forma, tudo é gratuito e ninguém precisa pagar absolutamente nada.

</div>
