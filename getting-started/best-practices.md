---
layout: docs
title: Boas práticas
group: getting-started
---

Geralmente a pior condição de trabalho para algum desenvolvedor, são trabalhos já existentes, pois normalmente cada desenvolvedor tem seu estilo próprio, nesse guia, criamos uma série de dicas que podem ajudar você e sua equipe a padronizar seu código. Tambem selecionamos algumas dicas e referências de acessibilidade para tornar seus sites acessíveis para aqueles que utilizam tecnologia assistiva.

## Conteúdo

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## Acessibilidade

É importante seguir padrões comuns web, &mdash; com um pouco de esforço &mdash; pode-se criar sites acessíveis para aqueles que utilizam <abbr title="Tecnologia assistiva" class="initialism">TA</abbr>.
{: .lead}

### Pular navegação

Se a navegação conter muitos links e vir antes do conteúdo principal da página, adicione um link `Pular para conteúdo principal` antes da navegação (para uma explicação simples, consulte este [Artigo Projeto A11y - Como usar link pular navegação (em inglês)](http://a11yproject.com/posts/skip-nav-links/){: title="Chromium bug tracker - Issue 262171: Focus should cycle from named anchor"}). Ao usar a classe `.sr-only` irá ocultar visualmente o link âncora, e a classe `.sr-only-focusable` irá garantir que o elemento só se tornará visível uma vez focada (para usuários que navegam com o teclado).

Devido a problemas de longa data / bugs no Chrome (veja a [issue 262171 in the Chromium bug tracker](https://code.google.com/p/chromium/issues/detail?id=262171)) e Internet Explorer (veja o artigo [in-page links and focus order](http://accessibleculture.org/articles/2010/05/in-page-links/)), Você vai precisar ter certeza de que o elemento de destino do seu link ancora é, esteja preparado para isso, para isso, basta adicionar o código `tabindex="-1"`.
Além disso, você pode não querer criar uma indicação explicita de que o elemento destino esteja realmente em foco com `#content:focus { outline: none; }`.
Note que este bug também afetará qualquer outro link ancora em seu site possa estar usando, tornando-os inúteis para usuários de teclado.
{: .alert .alert-danger}

{% highlight html %}
<body>
  <a href="#content" class="sr-only sr-only-focusable">Pular para conteúdo principal</a>
  ...
  <div id="content" tabindex="-1">
    <!-- Conteúdo principal da página -->
  </div>
</body>
{% endhighlight %}

### Hierarquia de cabeçalhos

Quando criamos uma hierarquia de cabeçalho (`<h1>` - `<h6>`), em seu documento, o cabeçalho principal deve ser `<h1>`. Em seguida cabeçalhos `<h2>` - `<h6>` devem vir de forma lógica, de tal modo que os leitores de telas consigam criar uma tabela de conteúdo para suas páginas.

Leia mais sobre [Cabeçalhos nível 1, sections e acessibilidade](http://tableless.com.br/cabecalhos-nivel-1-e-sections/) e [Entendendo o Outline do HTML](http://tableless.com.br/entendendo-o-outline-html/).

### Recursos adicionais

- [Boas práticas de Acessibilidade](http://tableless.com.br/boas-praticas-de-acessibilidade/)
- [Tecnologia assistiva – Wikipédia](https://pt.wikipedia.org/wiki/Tecnologia_assistiva)
- [Acessibilidade web - Wikipédia](https://pt.wikipedia.org/wiki/Acessibilidade_web)
- [Introdução à Acessibilidade na Web](http://www.maujor.com/w3c/introwac.html)
- [Cartilha Acessibilidade Na Web - W3c Brasil (pdf)](http://www.w3c.br/pub/Materiais/PublicacoesW3C/cartilha-w3cbr-acessibilidade-web-fasciculo-I.pdf)
- [Curso eMAG / Desenvolvedor](http://emag.governoeletronico.gov.br/cursodesenvolvedor/index.html)
- [e-MAG Checklist de Acessibilidade Manual para o Desenvolvedor](http://bit.ly/1ehmmIj)
- ["HTML Codesniffer" bookmarklet for identifying accessibility issues](https://github.com/squizlabs/HTML_CodeSniffer)
- [Chrome's Accessibility Developer Tools extension](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)
- [Colour Contrast Ana](http://www.paciellogroup.com/resources/contrastanalyser/)
- [The A11Y Project](http://a11yproject.com/)
- [MDN accessibility documentation](https://developer.mozilla.org/en-US/docs/Accessibility)

## EditorConfig

O [EditorConfig](http://editorconfig.org/) ajuda a definir e manter estilos de códigos consistentes entre diversos editores. Ele é um simples arquivo que guarda as configurações de estilo do código, o seu editor predileto lê estas configurações e entende exatamente qual a configuração utilizar para cada formato de arquivo. Leia mais [sobre o editorconfig](http://tableless.com.br/editorconfig/).

Configuração padrão do {{ site.title }}.

{% highlight html %}
# editorconfig.org

root = true

[*]
charset = utf-8
end_of_line = lf
indent_size = 2
indent_style = space
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]
trim_trailing_whitespace = false

[*.py]
indent_size = 4
{% endhighlight %}

## HTML

Dicas de formatação para deixar seu código HTML mais organizado, legível e semântico. Procure sempre usar a [ferramenta de validação da W3C](http://validator.w3.org/), eles sabem o que fazem.
{: .lead}

### Formatação geral

- Use tabulação com dois espaço de identação.
- Parágrafos de texto devem ser sempre colocados dentro da tag `<p>`. Nunca use várias vezes a tag `<br>`.
- Itens em formato de lista devem estar sempre em `<ul>`, `<ol>` ou `<dl>`. Nunca use um conjunto de `<div>` ou `<p>`.
- Cada campo do formulário que tem o texto anexado deve utilizar a tag `<label>`. Especialmente os tipo `radio` ou elementos `checkbox`.
- Apesar das aspas em torno do atributos ser opcional, sempre coloque aspas em torno dos atributos para facilitar a leitura.
- Evite escrever comentários de fechamento da tag, como `<!-- /.element -->`. Isso só acrescenta mais tempo de carregamento da página..
- Evite adicionar barra em elementos de fecho automático. Por exemplo, `<br>`, `<hr>`, `<img>`, e `<input>`.

### Atributos booleanos

Muitos atributos não necessitam de um valor para ser usado. Como `disabled` ou `checked`, então não use-os.

{% highlight html %}
<!-- Ruim -->
<input type="text" disabled="disabled">

<input type="checkbox" value="1" checked="checked">

<select>
  <option value="1" selected="selected">1</option>
</select>

<!-- Bom -->
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
  <option value="1" selected>1</option>
</select>
{% endhighlight %}

## CSS

Escreva código CSS de forma consciente.

### Prefixos de Nomenclatura

Usamos o prefixo `cps-` para todas as classes do {{ site.title }}. Isso nos ajuda a evitar conflitos com o CSS do produto de terceiros ou com outros frameworks.

### Utilização (classes vs. ids)

Devemos usar IDs para elementos que aparecem exatamente uma única vez em uma página, caso contrário, use classes. Em caso de dúvida, use um nome de classe.

- **Bons** candidatos para IDs são: cabeçalho, rodapé, janela modal.
- **Ruins** candidatos para IDs são: navegações, lista de itens, títulos.

### Aspas

Utilize **aspas duplas**.

{% highlight css %}
/* Ruim */
input[type='text'] { ... }
div:after { content: '...'; }

/* Bom */
input[type="text"] { ... }
div:after { content: "..."; }
{% endhighlight %}
