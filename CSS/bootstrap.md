### Screen Size
---
#### MIN
~~~css
 @media (min-width: @screen-sm-min) // >= 768px             /*(small tablet)*/
 @media (min-width: @screen-md-min) // >= 992px             /*(medium laptop)*/
 @media (min-width: @screen-lg-min) // >= 1200px            /*(large desktop)*/
---
~~~
---
#### MAX
~~~css
@media (max-width: @screen-xs-max) { // < 768px             /*(xsmall phone)*/
@media (max-width: @screen-sm-max) { // < 992px             /*(small tablet)*/
@media (max-width: @screen-md-max) { // < 1200px            /*(medium laptop)*/
~~~
---

#### Utilities
+ Utilitários de texto utilizados para ajustar o alinhamento, capitalização e outras propriedades de texto. 
---
~~~css
.pull-left                                                  /*alinha elementos à esquerda*/
.pull-right                                                 /*alinha elementos à direita*/
.hidden-{xs,sm,md,lg}                                       /*controla a visibilidade de elementos em diferentes tamanhos de tela, escondendo*/
.visible-{xs,sm,md,lg}                                      /*controla a visibilidade de elementos em diferentes tamanhos de tela, mostrando*/
.visible-{xs,sm,md,lg,print}-{block,inline,inline-block}    /*controla a exibição de elementos em diferentes tipos de mídia*/
.center-block  /* margin: auto */                           /*centraliza um elemento horizontalmente na página*/
.clearfix                                                   /*limpa o layout flutuante*/
.text-{center,left,right,justify,nowrap}                    /*alinha o texto*/
.text-{lowercase,uppercase,capitalize}                      /*define o estilo do texto*/
.show                                                       /*mostra elementos*/
.hidden                                                     /*esconde elementos*/
~~~
---

#### Columns

+ Utilizados para criar layouts responsivos e ajustar o posicionamento dos elementos em diferentes tamanhos de tela.
---
~~~css
.container                                                  /*define um container fixo com largura máxima responsiva*/
.container-fluid                                            /*define um container fluido que ocupa toda a largura da tela*/

/*as classes abaixo são usadas para definir as colunas de um layout responsivo baseado em grid, com diferentes tamanhos para diferentes tamanhos de tela.*/

.col-xs-1                                                   /*(xsmall phone)*/
.col-sm-1                                                   /*(small tablet)*/
.col-md-1                                                   /*(medium laptop)*/
.col-lg-1                                                   /*(large desktop)*/
.col-md-offset-1                                            /*define um deslocamento de coluna, permitindo empurrar as colunas para a direita em telas médias*/
~~~
---
   #### Mixins:
   + Classes utilizadas em conjunto com as classes de contêiner e coluna para criar layouts responsivos que se adaptam a diferentes tamanhos de tela e dispositivos.
---
~~~css
 @include make-xs-column(12);                               /*define que o elemento ocupará 12 colunas em telas extra pequenas*/
 @include make-sm-column(6);                                /*define que o elemento ocupará 6 colunas em telas pequenas*/
 @include make-md-column(3);                                /*define que o elemento ocupará 3 colunas em telas médias*/
 @include make-lg-column(3);                                /*define que o elemento ocupará 3 colunas em telas grandes*/
 @include make-sm-column-offset(1);                         /*define que o elemento terá um deslocamento de 1 coluna em telas pequenas*/
 @include make-sm-column-push(1);                           /*define que o elemento terá um afastamento de 1 coluna em telas pequenas*/
 @include make-sm-column-pull(1);                           /*define que o elemento terá um recuo de 1 coluna em telas pequenas*/
~~~
---
#### Modal
+ Estrutura básica para criar um modal (janela pop-up) com bootstrap
---
~~~css
<a data-toggle='modal' data-target='#new'>                         /*o data-toggle especifica o comportamento do elemento, que neste caso é para abrir um modal*/
                                                                   /*Já o data-target" é usado para especificar o ID do modal a ser aberto*/
#new.modal.fade(role='dialog')                                     /*define o ID e as classes do modal*/
  .modal-dialog // .modal-lg, .modal-sm                            /*define o contêiner que envolve o conteúdo do modal e pode ser estendida com as classes ".modal-lg" ou ".modal-sm" para controlar o tamanho do modal*/
    .modal-content                                                 /*define o estilo da janela modal e agrupa o conteúdo do modal*/
      .modal-header                                                /*cria um cabeçalho para o modal e a tag h4 com a classe*/
        %h4.modal-title hello                                      /*define o título do modal*/
        %button.close{type: 'button', data: { dismiss: 'modal' }}  /*botão close é criado e o atributo data-dismiss é definido como modal para fechar o modal quando o botão é clicado*/
          %span{'aria-hidden' => true}!= "&times;"
          %span.sr-only Close
      .modal-body                                                  /*define o conteúdo principal do modal*/
        ...
      .modal-footer                                                /*define um rodapé para o modal*/
        ...
  ~~~
  ---
 #### Modal via ajax (Rails)
   ---
   ~~~css
    %button.btn{data: { |                                   /*define um botão e que possui os atributos "data-toggle", "data-target" e "data-remote"*/
      toggle: 'modal', |                                    /*define o comportamento do botão como um modal*/
      target: '#chooseTheme', |                             /*indica o ID do modal a ser exibido*/
      remote: '/path/to/remote'}                            /*especifica a URL do arquivo remoto que contém o conteúdo do modal e permite que ele seja carregado dinamicamente sem precisar carregar a página inteira*/
      
      
  .modal.fade#chooseTheme                                  /*cria um modelo de diálogo (modal) com uma classe .modal e um ID #chooseTheme. A classe .fade é usada para adicionar um efeito de fade na transição do modal*/
    .modal-dialog.modal-xl                                  /*define o tamanho do modal, que é definido como 'modal-xl' neste caso*/
      .modal-content                                        /*define o estilo do modal e agrupa seu conteúdo*/
        .modal-header                                       /*cria um cabeçalho com um título definido pelo elemento h4 com a classe .modal-title*/
          %h4.modal-title                                   

        .modal-body                                         /*define o conteúdo principal do modal*/
          .spinner-panel.-lg                                /*adiciona um painel giratório com tamanho grande*/
            %i                                              /*O símbolo % é usado para indicar o início de um elemento HTML e o elemento <i> é usado para adicionar um ícone*/
   ~~~
  ---
#### Tooltip
+ Cria e adiciona uma dica de ferramenta a um elemento HTML específico.
    - O código HTML inclui um elemento "span" com atributos específicos para definir o posicionamento e o conteúdo da dica de ferramenta
    - Os atributos do elemento incluem "data-toggle", "title" e "data-placement", que são usados para definir as configurações do Tooltip.
    - O código JavaScript é usado para inicializar a funcionalidade do Tooltip nos elementos especificados.
  ---
~~~css
<span
  data-toggle='tooltip'                                     /*define o tipo de interação que acionará o Tooltip*/
  title='tooltip'                                           /*"title" define o texto que será mostrado no Tooltip*/
  data-placement='left|top|bottom|right'>                   /*define a posição do Tooltip em relação ao elemento*/
$(function () {
  $('[data-toogle~="tooltip"]').tooltip()                   /*classe JavaScript tooltip() é chamada para inicializar o comportamento da dica de ferramenta*/
})
/*o seletor '[data-toogle~="tooltip"]' é usado para selecionar todos os elementos que contêm o atributo data-toggle com o valor tooltip*/
~~~
---
#### Input groups
+ Cria um grupo de entrada de dados que permite aos usuários inserir informações em um formulário.
    - A classe "input-group" é aplicada a um elemento pai que contém um campo de entrada de texto (definido como um elemento com a classe "form-control") e um elemento "input-group-addon" que exibe "years" ao lado do campo de entrada.
+ Esse grupo de entrada de dados é útil para coletar informações relacionadas e exibi-las juntas no formulário. 
+ O resultado é um campo de entrada de texto com um addon que pode ser utilizado para fornecer informações adicionais ao usuário.
---
~~~css
.input-group                                                /*envolve o input e o addon, criando assim um grupo de entrada.*/
    input.form-control(type='text')                         /*O input é definido com a classe .form-control para aplicar o estilo do Bootstrap*/
    .input-group-addon years                                /*um addon é adicionado utilizando a tag span com esta classe onde o texto "years" é adicionado ao addon*/
  ~~~
