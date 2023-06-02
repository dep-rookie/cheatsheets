<h4>MySQL é um sistema de gerenciamento de banco de dados relacional usado para armazenar, organizar e recuperar dados de maneira eficiente.</h4>

---
### Browsing
---
~~~MySQL
SHOW DATABASES;                           
#mostra uma lista de todos os bancos de dados no servidor MySQL ao qual o usuário atual está conectado.

SHOW TABLES;
#mostra uma lista de todas as tabelas no banco de dados atual.

SHOW FIELDS FROM table / DESCRIBE table;
#mostra informações sobre as colunas de uma tabela específica, como nomes de coluna, tipos de dados, chaves primárias e valores padrão.

SHOW CREATE TABLE table;
#mostra a consulta SQL usada para criar uma tabela específica.

SHOW PROCESSLIST;
#mostra informações sobre os processos em execução no servidor MySQL ao qual o usuário atual está conectado.

KILL process_number;
#interrompe um processo em execução no servidor MySQL usando seu número de identificação de processo.
~~~
---
### Select
+ SELECT é usado para selecionar colunas específicas de tabelas em um banco de dados
---
~~~MySQL
SELECT * FROM table;
#seleciona todos os campos da tabela especificada

SELECT * FROM table1, table2;
#seleciona todos os campos de duas tabelas

SELECT field1, field2 FROM table1, table2;
#seleciona campos específicos de duas tabelas

SELECT ... FROM ... WHERE condition
#usa a cláusula WHERE para selecionar registros que atendem a uma condição

SELECT ... FROM ... WHERE condition GROUP BY field;
#adiciona cláusula GROUP BY para agrupar e filtrar resultados

SELECT ... FROM ... WHERE condition GROUP BY field HAVING condition2;
#adiciona cláusula HAVING para agrupar e filtrar resultados

SELECT ... FROM ... WHERE condition ORDER BY field1, field2;
#adiciona cláusulas ORDER BY para classificar resultados em ordem ascendente

SELECT ... FROM ... WHERE condition ORDER BY field1, field2 DESC;
#adiciona cláusulas ORDER BY para classificar resultados em ordem descendente

SELECT ... FROM ... WHERE condition LIMIT 10;
#usa a cláusula LIMIT para limitar o número de resultados

SELECT DISTINCT field1 FROM ...
#usa a cláusula DISTINCT para selecionar um valor único de um campo específico

SELECT DISTINCT field1, field2 FROM ...
#seleciona valores de campos específicos
~~~
---
### Select - Join
+ A cláusula FROM é usada para especificar as tabelas a partir das quais os dados serão selecionados
+ A cláusula JOIN é usada para combinar dados de várias tabelas com base em uma condição específica
+ A cláusula LEFT JOIN garante que todos os registros da tabela t1 sejam incluídos na consulta, mesmo que não haja correspondência na tabela t2.
+ A cláusula WHERE é opcional, mas é usada para filtrar os dados selecionados com base em uma ou mais condições
+ A cláusula ON especifica as condições de junção para combinar as tabelas
---
~~~MySQL
SELECT ... FROM t1 JOIN t2 ON t1.id1 = t2.id2 WHERE condition;
#usada para combinar os dados da tabela t1 com os dados da tabela t2, onde a coluna id1 da tabela t1 é igual à coluna id2 da tabela t2

SELECT ... FROM t1 LEFT JOIN t2 ON t1.id1 = t2.id2 WHERE condition;
#executa uma consulta em duas tabelas, t1 e t2, usando JOIN para combinar os dados das duas tabelas com base em uma condição específica
#no caso, a condição é que as colunas id1 e id2 correspondam entre as duas tabelas
#o resultado da consulta é uma tabela que contém todas as colunas selecionadas da tabela t1 e t2, onde a condição especificada é verdadeira

SELECT ... FROM t1 JOIN (t2 JOIN t3 ON ...) ON ...
#combina dados de três tabelas (t1, t2 e t3) com base em uma ou mais condições especificadas após ON. 
#a sintaxe geral é "FROM table1 JOIN table2 ON condition1 JOIN table3 ON condition2 ..."
#neste caso, a junção é realizada primeiro entre as tabelas t2 e t3 e, em seguida, os dados são combinados com a tabela t1.
~~~
---
### Create / Open / Delete Database
+ Além do MySQL, esses comandos podem ser usados em outros sistemas de gerenciamento de banco de dados relacionais (RDBMS)
---
~~~MySQL
CREATE DATABASE DatabaseName;
#cria um novo banco de dados com o nome "DatabaseName"

CREATE DATABASE DatabaseName CHARACTER SET utf8;
#cria um novo banco de dados com o nome "DatabaseName" e especifica que ele usará o conjunto de caracteres utf8

USE DatabaseName;
#seleciona o banco de dados "DatabaseName" para ser usado em consultas subsequentes

DROP DATABASE DatabaseName;
#exclui o banco de dados "DatabaseName" e todos os seus dados

ALTER DATABASE DatabaseName CHARACTER SET utf8;
#altera o conjunto de caracteres do banco de dados "DatabaseName" para utf8
~~~
---
### Conditions
---
~~~MySQL
field1 = value1
#corresponde a linhas onde field1 é igual a value1

field1 <> value1
#corresponde a linhas onde field1 não é igual a value1

field1 LIKE 'value _ %'
#corresponde a linhas onde field1 começa com value, seguido por qualquer caractere único, por zero ou mais caracteres

field1 IS NULL
#corresponde a linhas onde field1 é nulo

field1 IS NOT NULL
#corresponde a linhas onde field1 não é nulo

field1 IS IN (value1, value2)
#corresponde a linhas onde field1 é igual a value1 ou value2

field1 IS NOT IN (value1, value2)
#corresponde a linhas onde field1 não é igual a value1 ou value2

condition1 AND condition2
#corresponde a linhas onde tanto condition1 quanto condition2 são verdadeiras

condition1 OR condition2
#corresponde a linhas onde condition1 ou condition2 é verdadeira
~~~
---
### Backup Database to SQL File
+ Faz um backup de um banco de dados MySQL em um arquivo SQL usando o comando mysqldump
---
~~~MySQL
mysqldump -u Username -p dbNameYouWant > databasename_backup.sql
#é preciso especificar o nome de usuário (-u) e o nome do banco de dados (dbNameYouWant), e redirecionar a saída para um arquivo (>)
#o arquivo SQL resultante contém todas as instruções SQL necessárias para recriar a estrutura e os dados do banco de dados
~~~
---
### Repair Tables After Unclean Shutdown
+ Repara tabelas em um banco de dados MySQL após uma desligamento incorreto usando o comando mysqlcheck
---
~~~MySQL
mysqlcheck --all-databases;
#verifica e repara todas as tabelas em todos os bancos de dados

mysqlcheck --all-databases --fast;
#verifica e repara tabelas que precisam apenas de uma correção rápida
~~~
---
### Insert
+ O comando INSERT é usado para inserir dados em uma tabela
+ O comando DELETE é usado para excluir dados de uma tabela   
---
~~~MySQL
INSERT INTO table1 (field1, field2) VALUES (value1, value2);
#se especifica a tabela e os campos nos quais deseja inserir os dados

Delete
#se especifica os valores que deseja inserir nesses campos

DELETE FROM table1 / TRUNCATE table1
#exclui todos os dados de uma tabela

DELETE FROM table1 WHERE condition
#exclui apenas os dados que correspondem a uma determinada condição

DELETE FROM table1, table2 WHERE table1.id1 =
  table2.id2 AND condition
#permite excluir dados de várias tabelas ao mesmo tempo, desde que haja uma condição que as relacione
~~~  
---
### Update
+ O comando UPDATE é usado para atualizar dados em uma tabela
---
~~~MySQL
UPDATE table1 SET field1=new_value1 WHERE condition;
#especifica a tabela e o campo que deseja atualizar, juntamente com o novo valor

UPDATE table1, table2 SET field1=new_value1, field2=new_value2, ... WHERE
  table1.id1 = table2.id2 AND condition;
#atualiza vários campos ao mesmo tempo e especificar uma condição que limite quais registros serão atualizados.
~~~
---
### Create / Delete / Modify Table
+ usado no SQL para criar e excluir tabelas em um banco de dados
---
#### Create
+ O comando CREATE TABLE é usado para criar uma nova tabela em um banco de dados
+ "ON UPDATE" e "ON DELETE" especificam o que acontece com os dados na tabela referenciada quando os dados na tabela atual são atualizados ou excluídos, respectivamente. 
    - As opções possíveis são "CASCADE", que atualiza ou exclui automaticamente os dados na tabela referenciada, ou "SET NULL", que define os valores na coluna de referência como NULL
~~~MySQL
CREATE TABLE table (field1 type1, field2 type2);
#a tabela é nomeada "table" e possui dois campos, "field1" com o tipo de dado "type1" e "field2" com o tipo de dado "type2"

CREATE TABLE table (field1 type1, field2 type2, INDEX (field));
#um índice é adicionado à coluna "field"

CREATE TABLE table (field1 type1, field2 type2, PRIMARY KEY (field1));
#"field1" é definido como a chave primária da tabela

CREATE TABLE table (field1 type1, field2 type2, PRIMARY KEY (field1,field2));
#uma chave primária composta é criada usando ambos "field1" e "field2"

CREATE TABLE table1 (fk_field1 type1, field2 type2, ...,
  FOREIGN KEY (fk_field1) REFERENCES table2 (t2_fieldA))
    [ON UPDATE|ON DELETE] [CASCADE|SET NULL]    
#cria uma nova tabela chamada "table1" com duas colunas, "fk_field1" e "field2", cada uma com um tipo de dado específico
#a linha "FOREIGN KEY (fk_field1) REFERENCES table2 (t2_fieldA)" cria uma restrição de chave estrangeira que referencia outra tabela, "table2", e especifica a coluna em "table2" que está sendo referenciada
#isso ajuda a manter a integridade referencial dos dados no banco de dados.
    
CREATE TABLE table1 (fk_field1 type1, fk_field2 type2, ...,
 FOREIGN KEY (fk_field1, fk_field2) REFERENCES table2 (t2_fieldA, t2_fieldB)) 
#uma nova tabela é chamada de table1 e contém duas colunas: fk_field1 e fk_field2, cada uma com um tipo de dados específico (type1 e type2, respectivamente).
#a linha FOREIGN KEY (fk_field1, fk_field2) é usada para criar uma chave estrangeira que faz referência a outra tabela, table2, e especifica as colunas em table2 que são referenciadas (t2_fieldA e t2_fieldB)
#significa que os valores inseridos nas colunas fk_field1 e fk_field2 em table1 devem corresponder a valores nas colunas t2_fieldA e t2_fieldB em table2. 
#essa restrição de chave estrangeira ajuda a manter a integridade referencial dos dados no banco de dados

CREATE TABLE table IF NOT EXISTS;
#cria uma nova tabela chamada "table" no banco de dados, caso a tabela ainda não exista. 
#isso é útil para evitar erros ao tentar criar uma tabela que já existe

CREATE TEMPORARY TABLE table;
#cria uma tabela temporária chamada "table". 
#as tabelas temporárias são criadas na memória do banco de dados e são usadas para armazenar dados temporários durante a execução de uma consulta ou transação.
#as tabelas temporárias são excluídas automaticamente quando a conexão com o banco de dados é encerrada.
~~~
---
#### Drop
+ O comando DROP TABLE é usado para excluir uma tabela existente em um banco de dados

---
~~~MySQL
DROP TABLE table;
#a sintaxe básica é "DROP TABLE nome_da_tabela"

DROP TABLE IF EXISTS table;
#permite que a instrução seja executada com segurança, pois verifica se a tabela existe antes de tentar excluí-la
#o comando também permite excluir várias tabelas com uma única instrução

DROP TABLE table1, table2, ...
#usado para excluir uma ou mais tabelas existentes de um banco de dados. 
#as tabelas especificadas após o comando DROP TABLE serão permanentemente excluídas, juntamente com todas as suas linhas e dados associados. 
#importante notar que esta operação não pode ser desfeita, portanto, deve ser usada com cautela. 
#se houver alguma restrição ou dependência referente às tabelas que estão sendo excluídas, o comando DROP TABLE não será executado

~~~
---
#### Alter
+ Usado para modificar a estrutura de uma tabela existente, modificando, adicionando ou removendo colunas, bem como para alterar as propriedades das colunas existentes, como o tipo de dados, a restrição NOT NULL e o valor padrão. 
+ Também é possível adicionar e excluir índices através do comando ALTER TABLE
+ A modificação da estrutura de uma tabela pode afetar a integridade dos dados armazenados nela e que as alterações devem ser feitas com cuidado
---
~~~MySQL
ALTER TABLE table MODIFY field1 type1
#usado para modificar a coluna "field1" da tabela "table" para o tipo de dados "type1"

ALTER TABLE table MODIFY field1 type1 NOT NULL ...
#adiciona a restrição "NOT NULL" à coluna "field1"

ALTER TABLE table CHANGE old_name_field1 new_name_field1 type1
#usado para alterar o nome da coluna "old_name_field1" para "new_name_field1" e alterar o tipo de dados para "type1"

ALTER TABLE table CHANGE old_name_field1 new_name_field1 type1 NOT NULL ...
#adiciona a restrição "NOT NULL" à coluna renomeada

ALTER TABLE table ALTER field1 SET DEFAULT ...
#define um valor padrão para a coluna "field1"

ALTER TABLE table ALTER field1 DROP DEFAULT
#remove o valor padrão da coluna "field1".

ALTER TABLE table ADD new_name_field1 type1
#adiciona uma nova coluna "new_name_field1" do tipo de dados "type1" à tabela "table"

ALTER TABLE table ADD new_name_field1 type1 FIRST
#adiciona a nova coluna "new_name_field1" como a primeira coluna da tabela

ALTER TABLE table ADD new_name_field1 type1 AFTER another_field
#adiciona a nova coluna "new_name_field1" após a coluna "another_field"

ALTER TABLE table DROP field1
#remove a coluna "field1" da tabela "table"

ALTER TABLE table ADD INDEX (field);
#adiciona um índice para acelerar as consultas na coluna "field"
~~~
---
#### Change field order
---
~~~MySQL
ALTER TABLE table MODIFY field1 type1 FIRST
#usado para mudar a ordem dos campos em uma tabela. Ele move o campo "field1" para a primeira posição

ALTER TABLE table MODIFY field1 type1 AFTER another_field
#usado para colocar o campo "field1" depois do campo "another_field"

ALTER TABLE table CHANGE old_name_field1 new_name_field1 type1 FIRST
#usado para renomear um campo em uma tabela e movê-lo para a primeira posição

ALTER TABLE table CHANGE old_name_field1 new_name_field1 type1 AFTER
  another_field
#usado para renomear um campo em uma tabela e colocá-lo depois do campo "another_field"  
  
~~~  
---
### Keys
+ Criação de chaves em uma tabela
---
~~~MySQL
CREATE TABLE table (..., PRIMARY KEY (field1, field2))
#cria uma chave primária composta pelos campos "field1" e "field2" na tabela "table"
#significa que esses campos serão únicos e não poderão conter valores nulos 
#a chave primária é usada para identificar exclusivamente cada registro na tabela

CREATE TABLE table (..., FOREIGN KEY (field1, field2) REFERENCES table2
(t2_field1, t2_field2))
#cria uma chave estrangeira que faz referência aos campos "t2_field1" e "t2_field2" na tabela "table2"
#essa chave estrangeira é criada nos campos "field1" e "field2" na tabela "table"
#a chave é usada para garantir a integridade referencial entre as tabelas, ou seja, os valores nos campos referenciados na tabela "table" precisam existir na tabela "table2"
#se um valor referenciado for removido da tabela "table2", a operação será impedida

~~~
---
### Users and Privileges
---
~~~MySQL
CREATE USER 'user'@'localhost';
#cria um usuário "user" no servidor local

GRANT ALL PRIVILEGES ON base.* TO 'user'@'localhost' IDENTIFIED BY 'password';
#concede ao usuário "user" todos os privilégios (ALL PRIVILEGES) na base de dados "base", com a senha "password"

GRANT SELECT, INSERT, DELETE ON base.* TO 'user'@'localhost' IDENTIFIED BY 'password';
#concede permissões específicas (SELECT, INSERT, DELETE) na base de dados "base" para o usuário "user" com a senha "password"

REVOKE ALL PRIVILEGES ON base.* FROM 'user'@'host'; -- one permission only
#revoga todos os privilégios na base de dados "base" para o usuário "user" no host "host"

REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'user'@'host'; -- all permissions
#revoga todos os privilégios e opções de concessão de permissões para o usuário "user" no host "host"

FLUSH PRIVILEGES;
#atualiza as permissões em tempo real

SET PASSWORD = PASSWORD('new_pass');
#altera a senha do usuário "user"

SET PASSWORD FOR 'user'@'host' = PASSWORD('new_pass');
#define uma nova senha para o usuário "user" no host "host"

SET PASSWORD = OLD_PASSWORD('new_pass');
#altera a senha do usuário "user" usando a função OLD_PASSWORD()

DROP USER 'user'@'host';
Host ‘%’ indicates any host.
#remove o usuário "user" no host "host"
#o comentário indica que o host "%" representa qualquer host

~~~
---
### Main Data Types

---
~~~MySQL
TINYINT (1o: -128 to +127)
SMALLINT (2o: +-65 000)
MEDIUMINT (3o: +-16 000 000)
INT (4o: +- 2 000 000 000)
BIGINT (8o: +-9.10^18)
#dados numéricos (TINYINT, SMALLINT, MEDIUMINT, INT e BIGINT) possuem diferentes tamanhos e intervalos de valores possíveis
#o tamanho é indicado pelo número de bytes utilizados para armazenar o valor

Precise interval: -(2^(8*N-1)) -> (2^8*N)-1
#intervalo preciso para um número inteiro é de -(2^(8N-1)) a (2^(8N)-1), onde N é o número de bytes usados para armazenar o número 
#por exemplo, para um inteiro de 2 bytes, o intervalo é -(2^(82-1)) a (2^(82)-1), ou seja, -32.768 a 32.767

⚠ INT(2) = “2 digits displayed” – NOT “number with 2 digits max”
#significa que o número de dígitos exibidos não limita o tamanho máximo do número
#por exemplo, o número 123456 será exibido como "123456" mesmo que o tipo de dados tenha sido definido como INT(2)

FLOAT(M,D)
DOUBLE(M,D)
FLOAT(D=0->53)
#utilizados para armazenar números decimais, com diferentes tamanhos e precisões


⚠ 8,3 -> 12345,678 – NOT 12345678,123!
#significa que o número de dígitos após a vírgula é limitado pelo tipo de dados. 
#se um número com mais dígitos após a vírgula for inserido, ele será arredondado ou truncado. 
#por exemplo, se o tipo de dados for DECIMAL(8,3), o número máximo que pode ser armazenado é 99999.999, não 99999999.123

TIME (HH:MM)
YEAR (AAAA)
DATE (AAAA-MM-JJ)
DATETIME (AAAA-MM-JJ HH:MM; années 1000->9999)
TIMESTAMP (like DATETIME, but 1970->2038, compatible with Unix)
#dados temporais (TIME, YEAR, DATE, DATETIME e TIMESTAMP) são utilizados para armazenar informações de tempo e datas

VARCHAR (single-line; explicit size)
TEXT (multi-lines; max size=65535)
BLOB (binary; max size=65535)
#tipos de dados de texto que permitem armazenar diferentes tipos de informações de texto e binárias, com diferentes tamanhos máximos

Variants for TEXT&BLOB: TINY (max=255), MEDIUM (max=~16000), and LONG (max=4Go). Ex: VARCHAR(32), TINYTEXT, LONGBLOB, MEDIUMTEXT
#"TEXT&BLOB" têm três variantes: TINY, MEDIUM e LONG, que têm tamanhos e limites máximos diferentes. 
#VARCHAR(32) é uma coluna que pode armazenar um texto de até 32 caracteres. 
#TINYTEXT pode armazenar até 255 caracteres
#MEDIUMTEXT pode armazenar até ~16000 caracteres
#LONGBLOB pode armazenar até 4Go de dados binários.

ENUM ('value1', 'value2', ...) -- (default NULL, or '' if NOT NULL)
#ENUM é um tipo de dados usado para armazenar uma lista de valores permitidos. 
#por exemplo, se tiver uma coluna "gender" em uma tabela, poderá definir o tipo de dados como ENUM ('male', 'female', 'other') para permitir apenas esses três valores. 
#o valor padrão é NULL, a menos que você especifique o contrário.

~~~
---
### Reset Root Password
---
~~~MySQL
$ /etc/init.d/mysql stop
#usado para parar o serviço MySQL que está em execução

$ mysqld_safe --skip-grant-tables
#usado para iniciar o servidor MySQL com as tabelas de permissão desabilitadas
#permite que o comando de atualização da senha seja executado sem a necessidade de autenticação

$ mysql 
mysql> UPDATE mysql.user SET password=PASSWORD('new_pass') WHERE user='root';
#usado para iniciar o cliente MySQL em outro terminal
#o comando "UPDATE mysql.user SET password=PASSWORD('new_pass') WHERE user='root'" é então usado para atualizar a senha do usuário root

$ /etc/init.d/mysql start
##depois que a senha é atualizada, o comando "/etc/init.d/mysql start" é usado para iniciar o serviço MySQL novamente 
#o processo mysqld_safe é finalizado usando o comando "Control + " no terminal em que o comando foi executado
~~~
---
### Restore from backup SQL File
---
~~~MySQL
mysql -u Username -p dbNameYouWant < databasename_backup.sql;
#usado para restaurar um banco de dados MySQL a partir de um arquivo de backup SQL a partir da sintaxe:
# mysql -u [nome de usuário que tem permissão para acessar o banco de dados] 
#-p [nome do banco de dados que se deseja restaurar] 
#< [nome do arquivo de backup que contém as informações do banco de dados].sql;
#ao executar esse comando, o MySQL irá ler o arquivo de backup SQL e restaurar o banco de dados especificado com todas as informações contidas no arquivo de backup.

~~~
