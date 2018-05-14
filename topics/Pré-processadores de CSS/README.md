## Pré-processadores de CSS 

### Por que usar?
* Sabemos que o CSS tem seus limites. Também sabemos sobre a lentidão inevitável com a qual a linguagem está sendo desenvolvida e implementada para navegadores. Os pré-processadores CSS foram projetados para fornecer uma solução para esses problemas.

* Os pré-processadores, com seus recursos avançados, ajudaram a obter códigos reutilizáveis, passíveis de manutenção e extensíveis no CSS. Ao usar um pré-processador, você pode aumentar facilmente sua produtividade e diminuir a quantidade de código que está gravando em um projeto.

* Hoje em dia desenvolver com css virou algo muito repetitivo e muitas vezes chato. Porém, existem ferramentas que podem auxiliar nessa questão. 

* Pré-processadores tornam seu desenvolvimento mais robusto e para muitos, mais divertido. 

* Apesar de haver muitas pessoas contra o uso de Pré Processadores, eles estão em alta e em várias situações podem ser requisitos para vagas de emprego.

***
### Mas afinal, o que são esses tais pré-processadores?
Basicamente é como se você programasse em uma linguagem de programação compilada. Você escreve na sintaxe definida (Less/Sass/Stylus) e o pré processador compila para CSS e então você acrescenta o arquivo CSS a sua página normalmente.

***
### Vantagens de usar pré-processadores
* Código mais limpo e organizado
* Utilização de variáveis, lógica e realização de cálculos
* Fácil manutenção e reaproveitamento de código
* Você pode organizar seu CSS em vários arquivos e unificá-los na compilação
* Funções por meio dos “mixins”
* Alinhamento e Heranças
* Acabar com aqueles arquivos .css com 50 mil linhas

***
### Quando ultilizar?
Então, depende muito do tamanho do projeto.

Se você irá desenvolver apenas uma página simples e pequena, talvez não seja o caso. Porém, quando se trata de sistemas ou até mesmo portais grandes ou, se você quer facilitar a manutenção desse código no futuro, vale muito a pena utilizar um pré-processador.

***
### Qual usar?
Empunhar o verdadeiro poder de um pré-processador de CSS é uma aventura. Existem inúmeras linguagens, sintaxes e recursos, todos prontos para uso agora.

Então, vamos comparar os três pré-processadores mais ultilizados atualmente.
#### Linguagem base
* [Sass](https://sass-lang.com/): Ruby
* [Less](http://lesscss.org/): JavaScript
* [Stylus](http://stylus-lang.com/): JavaScript

***
#### Sintaxe
A parte mais importante de escrever código em um pré-processador de CSS é entender a sintaxe. Felizmente para nós, a sintaxe é (ou pode ser) idêntica ao CSS regular para todos os três pré-processadores. SASS e Stylus possuem estilos adicionais. No SASS, você pode omitir chaves e ponto e vírgula, enquanto na Stylus, você também pode omitir dois pontos. Estes são opcionais em SASS e Stylus.

Sass e LESS usam a sintaxe CSS padrão. Isso torna extremamente fácil converter um arquivo CSS existente em qualquer pré-processador. O Sass usa a extensão de arquivo .scss e o LESS usa a extensão de arquivo .less. O arquivo básico Sass ou LESS pode ser configurado como o exemplo abaixo:
     
     /* style.scss ou style.less */
    h2 {
      color: #fff;
    }
    
Como você deve ter notado, isso é apenas CSS regular, que compila perfeitamente tanto no Sass quanto no LESS.

É importante lembrar que o Sass também possui uma sintaxe antiga, que omite ponto e vírgula e chaves. Embora isso ainda esteja por aí, é antigo e não vamos usar além desse exemplo. A sintaxe usa a extensão de arquivo .sass. È mais ou menos assim:
    
    /* style.sass */
    h1
      color: #000
   
    h2
      color: #fff
   
   
Já sintaxe para Stylus é muito mais detalhada. Usando a extensão de arquivo .styl, o Stylus aceita a sintaxe CSS padrão, mas também aceita outras variações nas quais colchetes, dois-pontos e ponto e vírgula são todos opcionais. Por exemplo: 

    /* style.styl */
    h2 {
      color: #fff;
    }

    /* omitindo colchetes */
    h2
      color: #fff;

    /* Omitindo dois pontos e ponto-e-virgula */
    h2
      color #fff
      
Usar variações diferentes na mesma folha de estilo também é válido, o codigo será compilado sem erros. Por exemplo:

    h1 {
      color #000
    }
    
    h2
      color: #fff

***
#### Variaveis
As variáveis são uma das funcionalidades que comunidade mais desejadava para o CSS. Maioria dos desenvolvedores queriam definir uma cor base e usá-la em todo o arquivo CSS, em vez de escrever a cor hexadecimal ou nomeada em uma propriedade a cada vez. O mesmo que "color", variáveis necessárias para "width", "font-size", "font-family", "border" etc.

Variáveis em SASS começam com sinal de "$", em LESS começam com o sinal de "@" e em Stylus começam sem prefixo. Tanto em SASS quanto em LESS, os valores são atribuídos com dois pontos (:) e em Stylus com sinal de igual (=). O exemplo abaixo mostra a diferença entre eles na pratica.
     
* CSS

      div {
         font-size: 1.2em;
      }

* Sass

      $font-size: 1.2em;

      div {    
         font-size: $font-size;
      }     
      
* Less

      @font-size: 1.2em;

      div {
         font-size: @font-size;
      }
      
* Stylus

       font-size = 1.2em

       div
           font-size font-size
           
***
#### Nesting
O CSS não possui hierarquia visual ao trabalhar com seletores filhos. Você tem que escrever seletores e suas combinações em linhas separadas. O aninhamento fornece uma hierarquia visual como no HTML e aumenta a legibilidade. Em alguns casos, o aninhamento causa superdimensionamento dos seletores e algo como um "trem de seleção", portanto, use-o com sabedoria.

* CSS

      ul { 
         margin: 0; 
      }
     
      ul li { 
         float: left;
      }
     
      ul a { 
         color: #f3f3f3;
     
      }
      ul a:hover {
         color: #2aa8dd;
      }
      
* Sass

      $default-color: #f3f3f3;
      $default-hover: #2aa8dd;

      ul {
          margin: 0;
          
          li {
              float: left;
          }

          a {
              color: $default-color;
 
              &:hover {
                  color: $default-hover;
              }
          }
      }
      
 * Less
 
       @default-color: #f3f3f3;
       @default-hover: #2aa8dd;

       ul {
           margin: 0;
          
           li {
               float: left;
           }
 
           a {
               color: $default-color;
  
               &:hover {
                   color: $default-hover;
               }
           }
       }
       
* Stylus

      default-color = #f3f3f3
      default-hover = #2aa8dd

      ul
          margin 0
          li
              float left
          a
              color default-color
              &:hover
                  color default-hover

***                  
#### Mixins
Mixins são conjuntos de definições que compilam de acordo com alguns parâmetros ou regras estáticas.

* CSS

      h1 {
         border: 5px solid #f3f3f3;
      }
      
      h1:hover {
         border-color: #ddd;
      }

* Sass

      @mixin default-border($width) {
          border: $width solid #f3f3f3;   

          &:hover {
              border-color: #ddd;
          }
      }

      h1 {
          @include default-border(3px);
      }
      
* Less  

      .default-border(@width) {
          border: @width solid #f3f3f3;   

          &:hover {
              border-color: #ddd;
          }
      }

      h1 {
          .default-border(3px);
      }
      
* Stylus

      default-border(w)
          border: n solid #f3f3f3
          &:hover
              border-color: #ddd 

      h1
          default-border(3px)

***
#### Extends
Os extends são úteis para compartilhar uma definição genérica com seletores em vez de copiá-la. Todos os seletores estendidos são agrupados em CSS compilado. O SASS estende todas as instâncias do seletor estendido que incluem seus seletores filhos e propriedades herdadas. No entanto, em LESS você pode selecionar cada instância do seletor estendido, adicionando o atributo "all" para estender o método ou você pode selecionar apenas a instância principal.

* CSS

      .some-class, p, ul{ 
         margin: 5px;
      }
 
      p { 
         border: 1px solid #ddd; 
      }
      
      ul { 
         color: #fff; 
         text-transform: uppercase;
      }

* Sass 

          .some-class { 
             margin: 5px;
          }

          p {
            @extend .some-class;
            border: 2px solid #ddd;
          }

          ul {
            @extend .some-class;
            color: #fff;
            text-transform: uppercase;
          }

* Less

      .some-class {
         margin: 5px; 
      }

      p {
        &:extend(.some-class);
        border: 2px solid #ddd;
      }

      ul {
        &:extend(.block);
        color: #fff;
        text-transform: uppercase;
      }
      
* Stylus

      .some-class
          margin 5px

      p
          @extend .some-class
          border 2px solid #ddd

      ul
          @extend .some-class
          color #fff
          text-transform uppercase
          
***
#### Operações de cor
Todos os três pré-processadores têm funções de cores. Você pode clarear a cor base ou saturá-la, você pode até misturar duas ou mais cores diferentes. Esse recurso não é muito essencial, mas é bom ter.

* Sass

      saturate($color, $amount)
      desaturate($color, $amount)
      lighten($color, $amount)
      darken($color, $amount)
      adjust-hue($color, $amount)
      opacify($color, $amount)
      transparentize($color, $amount)
      mix($color1, $color2[, $amount])
      grayscale($color)
      complement($color)
     
* Less

      saturate(@color, @amount)
      desaturate(@color, @amount)
      lighten(@color, @amount)
      darken(@color, @amount)
      fadein(@color, @amount)
      fadeout(@color, @amount)
      fade(@color, @amount)
      spin(@color, @amount)
      mix(@color1, @color2, @weight)
      grayscale(@color)
      contrast(@color)
      
* Stylus

      red(color)
      green(color)
      blue(color)
      alpha(color)
      dark(color)
      light(color)
      hue(color)
      saturation(color)
      lightness(color)  
      
***
#### If / Else
As diretivas e expressões de controle ajudam a construir definições de estilo semelhantes de acordo com condições ou variáveis correspondentes. SASS e Stylus suportam condicionais normais if / else. Mas, em Less, você pode conseguir isso com  CSS Guards.

* Sass

      @if lightness($color) > 10% {
          background-color: #000;
      }
 
      @else {
         background-color: #fff;
      } 
      
* Less

      mixin (@color) when (lightness(@color) > 10%) {
         background-color: #000
      
      mixin (@color) when (lightness(@color) =<; 10%) {
         background-color: #fff;
      }
      
* Stylus

      if lightness(color) > 10%
          background-color #000
      else
          background-color #fff
          
***
#### Loops
Os loops são úteis ao iterar por um array ou criar uma série de estilos, como nas larguras de grid. Como no caso if / else, o LESS está usando CSS Guards e mixins recursivos para looping.

* Sass

      @for $i from 1px to 10px {
          .border-#{i} {
              border: $i solid #ddd;
          }
      }
      
 * Less 
 
       .loop(@count) when (@count > 0){
          .loop((@count - 1));
 
          .border-@{count} {
              border: 1px * @counter solid #ddd;
          }
       }
       
* Stylus

      for num in (1..10)
          .border-{num}
              border 1px * num solid #ddd
              
***
#### Math 
As operações matemáticas podem ser usadas para conversões aritméticas ou de unidades padrão. SASS e Stylus suportam aritmética entre diferentes unidades. Além de matemática simples, os pré-processadores também têm suporte matemático complexo, como arredondamento, obtenção de valor mínimo ou máximo em uma lista, etc.

* Sass

      1cm * 1em => 1 cm * em
       2in * 3in => 6 in * in
      (1cm / 1em) * 4em => 4cm
      2in + 3cm + 2pc => 3.514in
      3in / 2in => 1.5

* Less

      1cm * 1em => 1cm * 1em
      2in * 3in => 6in
      (1cm / 1em) * 4em => 4cm
      2in + 3cm + 2pc => 3.514in
      3in / 2in => 1.5in

* Stylus

      1cm * 1em => 1 cm * em
      2in * 3in => 6in
      (1cm / 1em) * 4em => 4cm
      2in + 3cm + 2pc => 5.181in
      3in / 2in => 1.5in
      
***
#### Imports
Em vez de usar um único arquivo grande, separar seus códigos em partes pequenas é útil para expressar suas declarações e aumentar a capacidade de manutenção e o controle sobre a base de código. Você pode agrupar os fragmentos de código semelhantes em pastas semelhantes e importá-los para o arquivo css/sass/scss principal. Também com o a instrução "import", os frameworks também podem ser adicionados aos pacotes de trabalho.

* Sass

      @import "library";
      @import "mixins/mixin.scss";
      @import "reset.css";

* Less

      @import "library"
      @import "mixins/mixin.less"
      @import "reset.css"

* Stylus

      @import "library"
      @import "mixins/mixin.styl"
      @import "reset.css
