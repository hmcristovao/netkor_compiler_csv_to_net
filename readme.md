# NetKOR Mapping Compiler
---
## Compilador para mapear arquivos CSV para Network 

Arquivo de entrada: CSV - cont�m a base de dados a ser mapeada

Arquivo de mapeamnento: MAP - cont�m a programa��o a ser usada no mapeamento do arquivo CVS para o formato Network

Arquivo de network: NET (default) - cont�m a sa�da a ser gerada pelo mapeamento realizado sobre o arquivo CSV

---

### Melhorias
#### A) Novas funcionalidades - N�vel de prioridade M�XIMO 
1. ~~Permitir a coloca��o de vari�veis de cabe�alho na se��o 3. Assim os n�s s�o criados usando-se os valores dessas vari�veis. Atualmente s�o permitidas apenas constantes.~~ 
2. ~~Em Section 2, permitir nome de identificador sozinho (sem dois pontos seguido de outro identificador). Nesse caso ele serve para identificar, com o mesmo nome, o cabe�alho de coluna do CSV e a vari�vel interna usada no MAP.~~
3. Cabe�alho das colunas do CSV: aceitar acentua��o e espa�os em branco. Nesse caso, a descri��o da coluna ficaria entre aspas. 
4. Tratar uma express�o do tipo data de calend�rio. Assim aceitar opera��es com os relacionais e intervalos.
5. Tratar uma express�o string alfabeticamente aceitando express�es alfab�ticas para definir intervalos. 
6. Implementar "Column separator:" em Section 1: permite configurar o caractere usado para separar os campos do CSV (o default seria a v�rgula). 
7. Implementar "Decimal separator:" em Section 1: permite configurar o caractere usado na separa��o decimal em n�meros reais. (o default seria o ponto). 
8. Implementar "Text delimiter:" em Section 1: permite configurar o caractere usado para envolver valores das colunas evitando  conflitos. Por exemplo, se a v�rgula � usada para separar campos e ao mesmo tempo como conte�do de um campo. 

#### B) Novas funcionalidades - N�vel de prioridade M�DIO
1. Permitir mesclagem de colunas. Exemplo do caso do documento Emendas.csv nas colunas nome Nome Subfun��o + � (� + Nome Fun��o + �)� 
2. Permitir o descarte de linhas que atendam um determinado crit�rio. Exemplo do caso do documento Emendas.csv onde foram descartadas 1500 linhas cujo crit�rio foi C�digo IBGE Estado = -2
3. Permitir a cria��o de colunas �virtuais� a partir de express�es envolvendo as colunas existentes. Por exemplo: coluna �nome do m�s� � a extra��o do m�s de uma data; coluna �taxa de feridos graves e mortos� � a raz�o da soma da qtde de feridos graves e mortos de um acidente pela qtde de ocupantes do ve�culo. 
4. Aceitar mistura de tipos. Exemplo, a coluna km cont�m a quilometragem do acidente, mas pode ter a string �NA� como n�o conhecido. Permitir que isso seja usado em express�es, tal como:
�km 0-10� : km <= 10
�Km NA� : km = �NA�

#### C) An�lise Sem�ntica
1. ~~Defini��o de vari�veis com nomes iguais~~
2. ~~Defini��o de uma vari�vel para duas ou mais colunas~~
3. Vari�vel n�o utilizada na defini��o dos v�rtices de incid�ncia (Klaus, isso deve ser um Warning!)
4. Verificar se todas as vari�veis usadas nas express�es da #Section 3 foram devidamente definidas em #Section 2.
5. V�rtices de incid�ncia com o mesmo nome (o que � isso Klaus?)

  
---
### Universidade Federal do Esp�rito Santo
#### Grupo de pesquisa NetKOR (Networked Knowledge Organization Retrieval)  
#### Desenvolvimento:
##### Coordenador
* Henrique Monteiro Cristov�o - hmcristovao@gmail.com
##### Colaboradores
* Klaus Kly Cuzzuol Wolff - darkkcw@gmail.com
* Luis Henrique Gundes Valim - henriquegundes@outlook.com
