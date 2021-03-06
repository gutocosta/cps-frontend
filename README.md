# CPS Front-end

Manual e framework front-end do Centro Paula Souza para projetos web.

## Conteúdo

* [Indrodução](#indrodução)
* [Instalação](#)
* [O que esta incluso](#)
* [Documentação](#)
* [Criadores](#)
* [Copyright e Licença](#)

## Indrodução

O objetivo do {{ site.title }} é oferecer uma nova ferramenta institucional para o desenvolvimento frond-end que, quando aplicada, ajudará na unificação do Centro Paula Souza, possibilitando deixar o site, seja da Fatec ou Etec, dentro das normas principais do manual de identidade disponibilizado pelo CPS, amigável visualmente e adaptável qualquer resolução de tela, facilitando sua acessibilidade.

## Instalação

É possivel fazer a instalação do {{ site.title }} (Atualmente na v{{ site.current_version }}) de duas maneiras, escolha a que for mais adequada às suas necessidades.

* [Baixar {{ site.title }}]({{ site.download.dist }}).
* [Instalar {{ site.title }} usando CDN (Rede de Distribuição de Conteúdo)]({{ "getting-started/install/#via-cdn-rede-de-distribuio-de-contedo" | prepend: site.baseurl | prepend: site.url }}).

### O que está incluso

Feito o download, descompacte a pasta compactada para ver a estrutura do {{ site.title }} (o compilado). Você verá algo parecido com isto:

```
cps-bootstrap/
├── css/
│   ├── cps.css
│   └── cps.min.css
├── js/
│   ├── cps.js
│   └── cps.min.js
└── brand/
    ├── cps/
    │   ├── logo.svg
    │   ├── logo-dark.svg
    │   ├── logo-gray.svg
    │   └── logo-light.svg
    ├── etec/
    │   ├── logo.svg
    │   ├── logo-dark.svg
    │   └── logo-light.svg
    ├── fatec/
    │   ├── logo.svg
    │   ├── logo-dark.svg
    │   └── logo-light.svg
    └── governo-sp/
        ├── logo.svg
        ├── logo-dark.svg
        └── logo-light.svg
```

Fornecemos os arquivos CSS e JS compilados (`cps.*`), tanto como  compilados e minificados (`cps.min.*`). Juntamente com os logos CPS, Etec, Fatec e Governo SP no formato `.svg`.

## Documentação

A documentação do {{ site.title }} é construída com [Jekyll](http://jekyllrb.com) e hospedada utilizando [GitHub Pages](https://pages.github.com).

## Criadores

**Adam Macias**

* <https://fb.com/adam.requena.macias>
* <https://github.com/adammacias>

**Flávia Souza**

* <https://fb.com/flaviacasouza>
* <https://github.com/flaviacs>

**Ramon Duran**

* <https://fb.com/anacristina.lobosilvaduran>
* <https://github.com/ramonduran>

## Copyright e Licença

Código e documentação copyright 2015 - {{ site.title }}. Todos os arquivos CSS, SCSS, JS e outros não incluindo arquivos de imagens estão licenciados como [GNU GENERAL PUBLIC LICENSE](https://github.com/adammacias/cps-bootstrap/blob/gh-pages/LICENSE) ou pela licença especificada dentro de seus arquivos.
