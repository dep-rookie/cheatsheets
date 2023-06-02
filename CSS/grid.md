*CSS Grid*
---
+ É uma ferramenta de layout em CSS que permite aos desenvolvedores criar layouts complexos e responsivos.
+ funciona criando uma grade flexível de linhas e colunas que podem ser usadas para posicionar os elementos de uma página da maneira desejada. 
+ Com o CSS Grid, é possível definir áreas, espaços em branco e lacunas entre elementos, além de definir as dimensões e a ordem dos elementos na grade. 
+ Isso torna muito mais fácil criar layouts complexos que funcionem bem em uma variedade de dispositivos e tamanhos de tela diferentes.
---


### Container
+ Usada no desenvolvimento de layouts responsivos para páginas web
+ A classe "grid-container" pode ser aplicada a um elemento HTML que contenha outros elementos filhos, como uma seção ou uma div que:
  - Definirá um contêiner com as propriedades necessárias para criar uma grade responsiva. 
+ Essas propriedades geralmente incluem largura, margens, preenchimento e exibição flexível.
---
~~~css
.grid-container {                                                 /*cria uma grade de elementos na página*/
~~~
---

  ### Display properties
  +  Propriedades de exibição do CSS controlam como um elemento HTML é exibido na página
  ---
 ~~~css
  display: grid;                                                  /*define um container como uma grade flexível, permitindo a criação de layouts complexos com várias linhas e colunas*/
  display: inline-grid;                                           /*faz o mesmo do código acima, mas permite que o container seja exibido como um elemento inline*/
  ~~~
  ---
  
  ### Columns and rows
  + Propriedades usadas para criar layouts responsivos e organizados em grades.
  + Define as colunas da grade, permitindo especificar a largura de cada coluna usando unidades de medida, porcentagens ou fr's (frações da largura disponível)
  + Podssibilidade de repetir colunas sem precisar escrevê-las repetidamente
  + Pode misturar diferentes unidades e regras para criar linhas de diferentes alturas. 
  + O valor subgrid permite que você use as trilhas de coluna ou linha definidas no grid pai.
  ---
  ~~~css
  grid-template-columns: 1rem 2rem 1rem;                          /*unidades de medida*/
  grid-template-columns: 25% 50% 25%;                             /*unidades de porcentagem*/
  grid-template-columns: 1rem auto 1rem 2fr;                      /*são definidas quatro colunas com larguras diferentes. A 1ª e 3ª têm uma largura fixa de 1rem, a 2ª se ajusta automaticamente ao conteúdo e a 4ª ocupa 2x a largura da 2ª coluna usando a unidade fr.*/
  grid-template-columns: repeat(12, 1fr);                         /*repete 12 colunas com largura igual usando a unidade fr, sem precisar escrever cada coluna individualmente*/
  grid-template-columns: subgrid;                                 /*utiliza as colunas definidas na grade pai para a grade atual, permitindo criar subgrades que se ajustam automaticamente às colunas da grade pai*/
  
  grid-template-rows: 1rem 10% auto repeat(5, 10px);              /*permite definir a altura das linhas da grade */
  grid-template-rows: subgrid;                                    /* Use row tracks defined on parent grid */
  ~~~
  ---
  ### Automatic columns and rows
  + Utilizado para definir o tamanho automático das colunas e linhas numa grade CSS
  + Quando definimos um valor, todas as colunas terão a mesma altura e/ou largura, independentemente do número de colunas de conteúdo que constam na grade.
  + Dessa forma, é possível criar grids de layout responsivo e organizado.
  ---
  ~~~css
  grid-auto-columns: 10px;                                        /*define o tamanho das colunas que serão criadas automaticamente, utilizando a unidade de medida px*/
  grid-auto-rows: 1rem;                                           /*define a altura das linhas que serão criadas automaticamente*/
  ~~~
  ---
  ### Areas
  + Utilizado para definir um layout de grid em CSS usando a propriedade grid-template-areas 
  + A disposição do grid é definida por uma grade de células, onde cada célula pode conter uma área nomeada
  + A definição de áreas permite que o conteúdo seja organizado de forma mais clara e estruturada em um layout de grid
  + Cada célula do grid é atribuída a um nome de área específico, que é definido por uma string com identificações correspondentes às células
  + Essa técnica permite criar layouts responsivos e bem organizados.
  ---
  ~~~css
  grid-template-areas:                                                  /*propriedade usada para definir as áreas correspondentes a cada célula da grade*/
    "header header"                                                     /*usada no estilo de bloco*/
    "main aside"                                                        /*usada no estilo de linha*/
    "footer footer";                                                    /*estilo de grade*/

  grid-template-areas: "header header" "main aside" "footer footer";    /*usada no estilo inline*/
  ~~~
