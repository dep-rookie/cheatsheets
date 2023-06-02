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
    "header header"                                                     /*header=cabeçalho. Usada no estilo de bloco*/
    "main aside"                                                        /*main=Seção principal; aside=Barra lateral. Usada no estilo de linha*/
    "footer footer";                                                    /*footer=Rodapé. Estilo de grade*/

  grid-template-areas: "header header" "main aside" "footer footer";    /*usada no estilo inline*/
  ~~~
  --- 
### Template shorthand
+ Usado para definir a estrutura de um layout de grade responsivo usando a propriedade grid-template
+ Podemos utilizar tanto uma sintaxe abreviada como uma sintaxe longa
+ A vantagem da sintaxe abreviada é que ela é mais concisa e fácil de ler, enquanto a sintaxe longa define as colunas e as linhas separadamente, além de definir     as áreas explícita e oferece mais controle sobre o layout.
---
 ~~~css
  grid-template:                                                     /*define a estrutura da grade*/
    "header header" auto                                             /*altura definida como automática*/
    "main aside" 100vh                                               /*altura total da viewport definida em pixels*/
    "footer footer" 10rem                                            /*define a altura da primeira linha como 10 unidades rem
    / 80% 20%;                                                       
    /*as barras (/) definem as colunas e seus tamanhos, onde 80% da largura é para a coluna principal e 20% para a secundária.*/

    /*O mesmo layout também pode ser definido usando as sintaxes abaixo, descrevendo a mesma estrutura com mais detalhes*/
   
  grid-template-columns: 80% 20%;
  grid-template-rows: auto 100vh 10rem;
  grid-template-areas:
    "header header"
    "main aside"
    "footer footer";                                     /*grade com duas linhas e uma coluna, na 1ª linha contém um elemento "footer" e a segunda está vazia*/
  ~~~
  ---
  ### Gaps
  + Espaço entre elementos em um layout de grade (grid layout). O espaço entre as células de uma grade é chamado de "gap". 
  + Definido usando a propriedade gap, que define a largura do espaço entre as células da grade. 
  + A propriedade gap permite definir um valor para a lacuna horizontal e verticalmente. 
      - Por exemplo, "gap: 10px 20px" define um espaço de 10 pixels na vertical e 20 pixels na horizontal, que ajuda a criar layouts mais limpos e organizados com        espaços uniformes entre elementos.


  + Usada para definir o espaçamento entre as células em uma grade CSS. As células são definidas pela propriedade "grid" e o espaçamento é definido pela               propriedade "gap". 
  ---
   ~~~css
  grid-row-gap: 1rem;                                     /*versão longa para definir valores separados para linhas e colunas*/
  grid-column-gap: 0.5rem;                                /*define um espaçamento de 1rem entre as linhas e um espaçamento de 0.5rem entre as colunas*/

  grid-gap: 1rem 0.5rem;                                  /*versão curta para definir o espaçamento para linhas e colunas de uma só vez */
  grid-gap: 1rem;                                         /*define um espaçamento de 1rem em ambas as dimensões*/
  ~~~
---  
 ### Item justification (horizontal or column alignment)
 + Propriedade usada para alinhamento horizontal ou de colunas em uma grade
 + A propriedade "justify-items" define o alinhamento horizontal dos itens dentro da grade
--- 
   ~~~css
  justify-items: start;                                   /*itens são alinhados à esquerda*/
  justify-items: center;                                  /*itens são são centralizados na coluna*/
  justify-items: end;                                     /*itens são alinhados à direita*/
  justify-items: stretch;                                 /*"stretch" (valor padrão), os itens são preenchidos na área disponível horizontalmente*/
  ~~~
---  
 ### Item alignment (vertical or row alignment)
 + Usado para alinhar verticalmente ou em linha os itens dentro da grade. 
 + A propriedade align-items tem quatro opções para alinhar os itens dentro da linha
---
   ~~~css
  align-items: start;                                     /*alinha os itens ao topo da linha*/
  align-items: center;                                    /*alinha os itens ao centro da linha*/
  align-items: end;                                       /*alinha os itens na parte inferior da linha*/
  align-items: stretch;                                   /*propriedade padrão que preenche a área disponível (verticalmente)*/
  ~~~
---
 ### Place item shorthand
 + Propriedade abreviada que combina as propriedades align-items e justify-items em uma
---
   ~~~css
  place-items: start stretch;                                           /*alinha os itens ao topo da linha e preenche o espaço vertical disponível*/

  /*O mesmo layout também pode ser definido usando as sintaxes abaixo*/
  
  align-items: start;
  justify-items: stretch;
  ~~~
---  
 ### Content justification (horizontal or column alignment)
 + Refere-se à forma como o conteúdo é alinhado horizontalmente dentro de um elemento. 
 + Existem quatro valores possíveis para a propriedade "text-align": "left", "right", "center" e "justify". 
    - O valor "left" alinha o texto à esquerda, enquanto o "right" o alinha à direita. 
    - "center" centraliza o texto no elemento e "justify" justifica o texto, expandindo os espaços entre as palavras para preencher o espaço disponível. 
 + A propriedade justify-content também é usada para alinhar os items dentro de um container em um layout de grade.
 ---
 ~~~css
  justify-content: start;                                      /*alinhamento à esquerda*/
  justify-content: center;                                     /*alinhamento ao centro horizontalmente*/
  justify-content: end;                                        /*alinhamento à direita*/
  justify-content: stretch;                                    /*alinha e preenche todo o espaço disponível de forma horizontal*/

  justify-content: space-around;                               /*define espaçamento igual entre cada item e as bordas no contêiner*/
  justify-content: space-between;                              /*define espaçamentos entre as colunas, sem margens na parte externa do conteúdo*/
  justify-content: space-evenly;                               /*adiciona um espaço uniforme entre os itens de um contêiner, incluindo o espaço nas extremidades*/
~~~
---
### Content alignment (horizontal or column alignment)
+ Processo de ajustar a posição do conteúdo de um elemento dentro de seu contêiner. 
    - Para alinhar horizontalmente um elemento, podemos utilizar "text-align", que define a posição do texto dentro de um elemento. 
    - Para alinhar colunas, podemos utilizar "justify-content", que define como os itens são distribuídos ao longo do eixo principal de um contêiner flex.
    - Além disso, a propriedade align-items pode ser usada para alinhar o conteúdo verticalmente dentro de um contêiner flex. 
+ Essas propriedades podem ser combinadas com outras propriedades de CSS para criar um layout personalizado para o seu site ou aplicação web.

---
~~~css
  align-content: start;                                        /*alinhamento ao topo*/
  align-content: center;                                       /*alinhamento ao centro*/
  align-content: end;                                          /*alinhamento na base do conteúdo*/
  align-content: stretch;                                      /*alinha e preenche todo o espaço disponível de forma vertical*/

  align-content: space-around;                                 /*define espaçamento do topo e parte inferior das linhas como margens superiores e inferiores*/
  align-content: space-between;                                /*Um espaço é selecionado para ficar entre as linhas, sem margens no lado de fora do conteúdo*/
  align-content: space-evenly;                                 /*Um espaço é selecionado para ficar uniformemente entre todas as linhas e bordas*/
~~~
---
### Place item shorthand
+ Propriedade encurtada que combina as propriedades align-content e justify-content
---
~~~css
  place-content: center start;                                /*alinha o conteúdo ao centro verticalmente e à esquerda horizontalmente*/
  align-content: center;                                      /*alinhamento ao centro*/
  justify-content: start;                                     /*define e alinha a  posição dos itens tanto no eixo principal quanto no eixo transversal*/
  
  /*se o eixo principal for horizontal, todos os itens serão alinhados no lado esquerdo do container, se a direção for da esquerda para a direita. Se a direção for da direita para a esquerda, todos os itens serão alinhados no lado direito do container*/
~~~
---
### Automatic grid positioning
+ Recurso que permite que os itens dentro de um grid sejam posicionados automaticamente, sem a necessidade de especificar manualmente as posições de cada item. 
+ Para ativar o recurso, definimos a propriedade "grid-auto-flow" com o valor "row" ou "column", dependendo do eixo do grid que se deseja posicionar                 automaticamente.
    - Por exemplo, definindo "grid-auto-flow: row", os itens serão posicionados automaticamente em linhas, preenchendo cada linha antes de ir para a                     próxima. 
    - Se definirmos "grid-auto-flow: column", os itens serão posicionados automaticamente em colunas, preenchendo cada coluna antes de passar para a próxima.
+ Também podemos usar a propriedade "grid-auto-rows" para definir a altura padrão das linhas automáticas e "grid-auto-columns" para definir a largura padrão das     colunas automáticas.

---
~~~css
  grid-auto-flow: row;                                        /*define a ordem das linhas da esquerda para direita, de cima para baixo*/
  grid-auto-flow: column;deixar o navegador decidir a ordem/*define a ordem das colunas de cima para baixo e da esquerda para direita*/
  grid-auto-flow: dense;                                      /*deixa o navegador decidir a melhor ordem com layouts avançados*/
~~~
---
### Explicit grid columns, rows, and areas
+ Define explicitamente as colunas, linhas e áreas de uma grade
+ A propriedade grid é uma forma abreviada de definir todas as propriedades do container de uma vez. 
+ É possível definir o tamanho das colunas e linhas, bem como as áreas do grid.
+ Áreas são definidas por uma string delimitada por aspas duplas, com cada linha da string representando uma linha da grade e cada célula separada por um espaço.
---
~~~css
  grid:                                                       
    "header header" auto                                       /*definida para se ajustar automaticamente ao conteúdo*/
    "main aside" 100vh                                         /*define altura de 100% da altura da viewport*/
    "footer footer" 10rem                                      /*define altura de 10rem*/
    / 80% 20%;                                                 /*define a primeira coluna com 80% da largura total e a segunda com 20% da largura total*/
  grid-template:                                               
    "header header" auto
    "main aside" 100vh
    "footer footer" 10rem
    / 80% 20%;                                                 /*mesmas definições das sintaxes acima*/
  grid-template-columns: 80% 20%;                              /*define explicitamente as dimensões das colunas*/
  grid-template-rows: auto 100vh 10rem;                        /*define explicitamente as dimensões das colunas*/
  grid-template-areas:                                         /*define as áreas nomeadas da grade, que podem ser referenciadas pelos seletores de elementos*/
    "header header"
    "main aside"
    "footer footer";
~~~
---
### Automatic grid flows
+ Define o posicionamento automático de grade, colunas, linhas e áreas de grade explícitas e fluxos automáticos de grade
+ Os fluxos automáticos de grade permitem definir linhas, fluxo e colunas automáticas
+ A propriedade "auto-flow" é usada para definir como o grid se comporta quando novos itens são adicionados
+ Quando definido como "row", novos itens são adicionados em novas linhas, enquanto "column" adiciona os itens em novas colunas. 
+ Além disso, a propriedade "auto-flow" também pode ser definida como "dense", o que garante que os itens sejam compactados no grid, mesmo que isso signifique       ignorar o espaço vazio.
---
 ~~~css
  grid: 1rem / auto-flow dense 1fr;                           /*a grade é configurada com uma única linha e as colunas são definidas como 1fr*/
  grid-template-rows: 1rem;                                   /*linhas são definidas como 1fr*/
  grid-auto-flow: dense;                                      /*garante que os itens sejam densamente compactados na grade*/
  grid-auto-columns: 1fr;                                     /*colunas são definidas como 1fr*/

  grid: auto-flow dense 1rem / repeat(10, 10%);               
  /*grade é configurada com linhas automáticas e colunas definidas, com dez colunas, cada uma ocupando 10% do espaço disponível e os itens são densamente compactados na grade.*/
  
  grid-auto-flow: dense;
  grid-auto-rows: 1rem;
  grid-template-columns: repeat(10, 10%);
 ~~~
 ---
### Child
+ Seletor usado para selecionar um elemento que é um filho direto de outro elemento.
+ Representado pelo sinal ">" sendo muito útil para selecionar elementos específicos dentro de uma hierarquia de elementos. 
    - Por exemplo, se quisermos selecionar apenas os elementos de lista que são filhos diretos de uma div, podemos usar o seletor "div > ul" para fazer isso. 
+ O seletor "child" pode ser combinado com outros seletores para criar seleções mais específicas e granulares.
---
~~~css
.grid-child {                                                     /*direciona os itens da grade e configura suas propriedades*/
~~~
---
### Column position
+ Define a posição horizontal de um elemento dentro de uma coluna em um layout de várias colunas, trabalhando em conjunto com a propriedade "column-count" que       define o número de colunas em um layout.
+ A propriedade "column-position" aceita os valores "auto", "start", "end", "center" e valores numéricos em porcentagem ou pixels. O valor padrão é auto, que       posiciona o elemento no início da coluna.
      - Por exemplo, a regra "column-position: center" posiciona o elemento no centro da coluna, enquanto "column-position: 25%" posiciona o elemento a 25% da             largura da coluna a partir do início. 
      - A propriedade "column-position" é útil para o alinhamento horizontal de elementos em layouts de várias colunas.
---
~~~css
  grid-column-start: 1;                                             /*permite definir pontos de início das colunas da grade*/
  grid-column-end: 2;                                               /*permite definir pontos de finalização das colunas da grade*/

  grid-column: 1 / 2;                                               /*define que o item ocupe a primeira coluna do grid*/
  grid-column: 1 / span 2;                                          /*define que o item ocupe duas colunas a partir da primeira coluna do grid*/
  grid-column: 1;                                                   /*define que o item ocupe apenas a primeira coluna do grid */
~~~
---
### Row position
+ Permite definir pontos de início e finalização de linhas da grade
+ A propriedade "grid-row" é uma forma abreviada de definir a posição vertical e o tamanho do item em uma única linha, permitindo que você defina o ponto de         partida e o ponto final ou use a palavra-chave "span" para definir o tamanho do item
---
~~~css
  grid-row-start: 2;                                               /*permite definir pontos de início das linhas da grade*/
  grid-row-end: 4;                                                 /*permite definir pontos de pontos de finalização das linhas da grade*/

  grid-row: 2 / 4;                                                 /*mesmas definições das sintaxes acima, de forma encurtada*/
  grid-row: 2 / span 3;                                            /*define 3 linhas sem definir explicitamente um ponto final*/
  grid-row: 1;                                                     /*define que o item começa e ocupa apenas uma linha*/
 ~~~
---
### Area positioning
+ Refere-se a como os elementos são posicionados uns em relação aos outros dentro de um contêiner. 
+ Uma forma de posicionar elementos é usando o grid layout, que permite definir áreas específicas dentro de uma grade e posicionando elementos dentro dessas         áreas.
    - Para posicionar elementos usando o grid layout, podemos usar as propriedades "grid-template-areas" e "grid-area". 
    - A primeira propriedade permite que você defina as áreas da grade para seus elementos, enquanto a segunda propriedade permite que você especifique em qual         área um elemento específico deve ser posicionado.

---
~~~css 
  grid-area: header;                                          /*posiciona o item nomeando a área selecionada*/

  grid-area: 2 / 1 / 4 / 2;                                   /*posiciona a partir de uma linha (2) de uma coluna (1) e se estende até a linha (4) da coluna 2)*/
  grid-row-start: 2;                                          /*onde o posicionamento da linha começa*/
  grid-column-start: 1;                                       /*onde o posicionamento da coluna começa*/
  grid-row-end: 4;                                            /*onde o posicionamento da linha termina*/
  grid-column-end: 2;                                         /*onde o posicionamento da coluna termina*/
~~~
---
### Self justification (horizontal or column alignment)
+ Refere-se ao posicionamento de um item dentro de sua própria célula de grade. Isso é feito usando a propriedade "justify-self", que pode receber valores como     "start", "end", "center" ou "stretch" para alinhar o conteúdo horizontalmente.
+ Propriedade úteis quando se deseja ajustar a posição de um único item em uma grade sem afetar os outros itens
---
~~~css
  justify-self: start;                                                /*alinhamento à esquerda*/
  justify-self: center;                                               /*alinhamento centralizado na coluna*/
  justify-self: end;                                                  /*alinhamento do item ao final da célula */
  justify-self: stretch;                                              /*valor padrão, que faz com que o item preencha a área disponível horizontalmente*/
~~~
### Self alignment (vertical or row alignment)
+ Refere-se ao posicionamento vertical de um item dentro de sua própria célula de grade. Isso é feito usando a propriedade "align-self", que pode receber valores   como "start", "end", "center" ou "stretch" assim como em "self justification" para alinhar o conteúdo verticalmente
+ Propriedades úteis para ajustar o posicionamento de um item individualmente dentro do seu contêiner, sem afetar os outros itens. 
+ Frequentemente usadas em layouts de grade (grid) para controlar o posicionamento dos elementos.
~~~css
  align-self: start;                                                  /*alinha o item no início do contêiner*/
  align-self: center;                                                 /*alinha o item no centro do contêiner*/
  align-self: end;                                                    /*alinha o item no final do contêiner*/
  align-self: stretch;                                                /*valor padrão, que faz com que o contêiner preencha a área disponível verticalmente*/
~~~
---
### Placement shorthand
+ Propriedade encurtada que combina as propriedades justify-self e align-self
    - "start" é usado para alinhar o item na borda inicial do seu contêiner e "stretch" é usado para esticar o item verticalmente para preencher todo o espaço            disponível na célula da grade
---
~~~css
  place-self: start stretch;                      
  /*alinha o item no início do seu contêiner e estica-o para preencher todo o espaço vertical da célula da grade*/

/*O mesmo layout também pode ser definido usando as sintaxes abaixo*/

   ~~~css
  align-self: start;
  justify-self: stretch;
}
~~~
