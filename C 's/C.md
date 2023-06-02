## Usados para modificar o código fonte antes de ser compilado, essas diretivas são úteis para tornar o código mais legível, modular e personalizável.
---
### Compiling
---
+ Processo de converter o código-fonte escrito em uma linguagem de programação de alto nível, em código de máquina que pode ser executado diretamente 
por um computador. 
+ O comando "$ cpp -P arquivo > arquivo_de_saida" é um exemplo de comando pré-processador em C++ que remove comentários e expande 
macros no código-fonte antes que ele seja compilado. 
+ O código de máquina resultante é tipicamente salvo em um arquivo de saída que pode ser executado pelo sistema operacional.
---
$ cpp -P file > outfile

----
### Includes
---
+ Diretiva de pré-processador que informa ao compilador para incluir o conteúdo de um arquivo no programa durante a fase de compilação. 
+ O arquivo é o nome do arquivo que você deseja incluir no programa. 
+ Você pode usar aspas duplas ou colchetes angulares para incluir o arquivo. Se você usar aspas duplas, o pré-processador procurará o arquivo no diretório atual. 
+ Se você usar colchetes angulares, o pré-processador procurará o arquivo nos diretórios padrão do sistema.
---
~~~C
#include "file"
~~~
----
### Defines
---
+ Diretiva de pré-processador que define uma macro. Uma macro é um trecho de código que recebe um nome.
+  Quando o nome é usado no programa, ele é substituído pelo código definido pela macro.
    -  define FOO: define uma macro com uma lista de substituição vazia
    -  define FOO "hello" define uma macro com a lista de substituição "hello"
    -  undef FOO remove a definição da macro
---
~~~C
#define FOO
#define FOO "hello"
#undef FOO
~~~~
---
### If
---
+ #ifdef / #ifndef / #if: são diretivas usadas para verificar se um determinado macro está definido, ou se uma condição é verdadeira.
---
~~~C
#ifdef DEBUG
  console.log('hi');
#elif defined VERBOSE
  ...
#else
  ...
#endif
~~~
---
### Error
---
+ #error / #warning: são diretivas que geram um erro ou um aviso de compilação.
---
~~~C
#if VERSION == 2.0
  #error Unsupported
  #warning Not really supported
#endif
~~~
---
### File and line
---
+ Macros pré-definidas que contêm o nome do arquivo e o número da linha em que a macro é usada.
---
~~~C
#define LOG(msg) console.log(__FILE__, __LINE__, msg)
#=> console.log("file.txt", 3, "hey")
~~~
---
### Macro
---
+ Sequência de instruções que é dada um nome e pode ser usada para substituir o código em um programa.
---
~~~C
#define DEG(x) ((x) * 57.29)
~~~
---
### Token concat
---
+ Técnica que permite combinar dois ou mais tokens em um único token.
---
~~~C
#define DST(name) name##_s name##_t
DST(object);   #=> object_s object_t;
~~~~
---
### Stringification
---
+ Técnica que permite converter um token em uma string.
---
~~~C
#define STR(name) #name
char * a = STR(object);   #=> char * a = "object";
~~~~
---
