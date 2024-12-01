# Tutorial de Prolog
- adicionar uma descrição
- adicionar uma introdução
- refazer imagens
- falar sobre variáveis nas regras

## Sumário
1. [Introdução](#ancora0)
2. [O que é Prolog?](#ancora1)  
3. [Instalação](#ancora2)
- [Online](#ancora2_1)
- [Para Windows](#ancora2-2)
- [Para Linux Ubuntu](#ancora2-3)
3. [Programando em Prolog](#ancora3)
  - [Fatos](#ancora3-1)
  - [Regras](#ancora3-2)
  - [Consultas](#ancora3-3)


<a id="ancora0"></a>
## Introdução
Lógica simbólica trata-se de abstrações que representam as características formais da inferência lógica. Ela é dividida em dois ramos principais: a lógica proposicional e a lógica de predicados. A mesma pode atender às três principais funções da lógica formal: representar proposições, definir relações entre elas e explicar como novas proposições podem ser deduzidas a partir de outras assumidas como verdadeiras.  
  
A programação que utiliza lógica simbólica como linguagem é conhecida como **Programação Lógica**, enquanto as linguagens baseadas nesse tipo de lógica são chamadas de linguagens de programação lógica ou linguagens declarativas. A execução de um programa declarativo permite ao usuário fazer perguntas para buscar informações sobre conclusões deduzidas a partir de hipóteses. Ao receber a pergunta, o programa ativa sua "máquina de inferência" e aplica regras lógicas às hipóteses para identificar quais conclusões respondem à questão. Neste tutorial, vamos utilizar o Prolog como linguagem por ser a mais amplamente usada.
  
<a id="ancora1"></a>
## O que é Prolog?  
Criada em 1972 por Alain Colmerauer e Philippe Roussel, Prolog, abreviação de PROgramming LOGic, é uma linguagem de programação baseada nas noções matemáticas de relações e inferência lógica. Prolog é considerado uma **linguagem declarativa**, o que significa que, diferentemente de linguagens procedurais como Pyhton, que descrevem o passo a passo de como computar uma resposta, Prolog consiste numa base de dados de **fatos e regras** que descrevem as relações que moldam o programa, o usuário então pode fazer uma **consulta** e o programa responde com base no banco de dados.  
  
Os **fatos** declaram relações ou caractertísticas para os itens de um conjunto universo. 
  
- *"Hoje está ensolarado"* atribui a característica "ensolarado" para o item "hoje" de um conjunto de dias;  
- *"João e Ana são irmãos"*  estabelece a relação "irmãos" aos itens "João" e "Ana" de um conjunto de pessoas
  
As **regras** são predicados condicionais, definem novas relações usando relações que já existem.  
- *"Vou sair se hoje estiver ensolarado"* estabelece uma regra, onde "sair" só acontece se "hoje estiver ensolarado" for verdade;  
- *"Se está chovendo e preciso sair, uso o guarda-chuva"*  define que apenas "uso o guarda-chuva" se "está chovendo" e "preciso sair" são verdades simultaneamente.
  
Por último, as **consultas** são o meio de solicitar informações de um banco de dados.  
- *"Marcos é pai de João"* (fato)  
- *"Marcos é pai de Lucas"* (fato)  
- *"X é filho de Y se Y é pai de X"* (regra)  
- *"Quem é filho de Marcos?"* (consulta)

Repare que X e Y funcionam como variáveis matemáticas na regra estabelecida. As variáveis serão melhor abordadas durante a seção (INSIRA SEÇÃO AQUI).
  
  
    
<a id="ancora2"></a>
## Instalação  

<a id="ancora2-2"></a>
### Online
Caso não queira instalar o ambiente do SWI Prolog, o mesmo possui uma versão online, o [SWISH](https://swish.swi-prolog.org). Ao acessar o link, você encontrará a seguinte tela:  
![tela inicial swish](imagens/tela_swish.png)
1. Clique no botão azul "Program" para criar um novo banco de dados Prolog.  
2. Escreva os fatos e regras do lado esquerdo. Para fazer consultas, utilize o terminal localizado no canto inferior direito.
![tela de edição](imagens/tela_edicao.png)
3. Para executar, clique no botão azul "Run!".
4. Se sua consulta possui vários resultados, clique em "Next". O terminal não oferecerá essa opção uma vez que todos os resultados possíveis forem exibidos.
![terminal swish](imagens/terminal.png)

<a id="ancora2-2"></a>
### Para Windows
1. Acesse o link <https://www.swi-prolog.org/download/stable>  
2. No bloco "Binaries" selecione a versão que melhor se adequa à sua máquina
![opções de download](imagens/downloads.png)  
3. Selecione a caixa "I understand" e clique no link de download logo abaixo
![link de download](imagens/confirma.png)
4. Após concluir o download, vá para o arquivo e execute-o para iniciar a instalação. É recomendado adicionar o ícone à tela inicial
5. Não esqueça de reiniciar a máquina após concluir a instalação
Se precisar de mais ajuda, tente verificar um [tutorial no YouTube](https://www.youtube.com/watch?v=vnGWJxl1Cbk)

<a id="ancora2-3"></a>
### Para Linux Ubuntu  
1. Execute as seguintes linhas de código no seu terminal:  
```
% sudo apt-add-repository ppa:swi-prolog/stable
% sudo apt-get update
% sudo apt-get install swi-prolog
```
2. Crie um arquivo .pl e edite o arquivo com o editor de texto de sua preferência, escrevendo os fatos e regras.
3. Volte para o terminal e escreva a seguinte linha, usando o nome do seu arquivo:
```
swipl -s arquivoProlog.pl
```
4. Escreva suas consultas no terminal.
  
<a id="ancora3"></a>
## Programando em Prolog

<a id="ancora3-1"></a>
### Fatos
Fatos são proposições consideradas verdadeiras. Em Prolog elas seguem a estrutura ***relação*(*itens que participam da relação*)** e são delimitados por um ponto final, tais como em:
- pai(marcos, joão).  
- nublado(hoje).
  
Note que Prolog não tem semântica intrínseca, logo, o significado dos fatos depende da interpretação do programador. A relação *pai(marcos, joão)* poderia significar que Marcos é pai de João, João é pai de Marcos ou que Marcos e João são pais. Por isso, tente ser claro ao nomear as relações.

<a id="ancora3-2"></a>
### Regras  
Sendo um condicional, as regras são compostas por um antecedente, que pode ser um termo simples ou uma conjunção, e caso este seja verdadeiro, gera um consequente, que é um termo simples. Para entender as regras em Prolog, é necessário saber também os operadores usados:  
| SÍMBOLO |   CONECTIVO  | OPERAÇÃO LÓGICA |
| :---:   |    :----:    |     :---:    |
| :-      | if (se)      | implicação   |
| ,       | and (e)      | conjunção    |
| ;       | or (ou)      | disjunção    |
| not     | not (não)    | negação      |  
  
Em Prolog, escrevemos o consequente primeiro e atribuímos uma condição a ele, seguindo a estrutura ***consequente* :- *expressão antecedente***, delimitando novamente com um ponto final, como em:
- presa(X) :- come(Y,X), animal(X).
  
Nesta regra, X é presa **se** Y come X **e** X é um animal. Ao escrever fatos e regras em Prolog, **use letras maiúsculas somente para representar variáveis**.

<a id="ancora3-3"></a>
### Consultas
A sintaxe das consultas em Prolog é bem semelhante a dos fatos. Para fazer uma consulta em Prolog, usamos ?- e escrevemos uma regra. O programa deve retornar todas os itens que atendem a esta regra. Observe o seguinte exemplo:  
Levando em consideração o seguinte banco de dados Prolog
```
pai(milton, maria).
pai(milton, juliano).
pai(ricardo, milton).
pai(leandro, andrea).
filho(X, Y) :- pai(Y, X).
neto(X, Z) :- pai(Z, Y), filho(X, Y).
```
Podemos perguntar *?-neto(X, ricardo)* para saber quem são os netos de ricardo. O programa deve responder "maria" e "juliano", sempre seguindo a ordem em que foram escritos no banco de dados. Independente se estiver usando o site SWISH ou a interface SWI Prolog, o ?- já é adicionado automaticamente, então não é necessário escrevê-lo.  
  
**Tente fazer os seguintes exercícios, utilizando o que aprendeu até agora**  
1. Gersting<sup>[[1]](#ref_gersting)</sup>, Problema prático 28  
   Dado o Banco de Dados:
```
come(urso, peixe).
come(urso, raposa).
come(veado, grama).
animal(urso).
animal(peixe).
animal(raposa).
animal(veado).
planta(grama).
```
Diga qual vai ser a resposta do programa à consulta *?-come(X, Y), planta(Y)*  

  
2. Gersting<sup>[[1]](#ref_gersting)</sup>, Problema prático 29  
   Dado o banco de dados:
```
come(urso, peixe).
come(peixe, peixinho).
come(peixinho, alga).
come(guaxinim, peixe).
come(urso, guaxinim).
come(urso, raposa).
come(raposa, coelho).
come(coelho, grama).
come(urso, veado).
come(veado, grama).
come(lince, veado).
animal(urso).
animal(peixe).
animal(peixinho).
animal(guaxinim).
animal(raposa).
animal(coelho).
animal(veado).
animal(lince).
planta(grama).
planta(alga).
presa(X) :- come(Y, X), animal(X).
```
&nbsp;&nbsp;a) Formule uma regra de Prolog que define o predicado predador.  
&nbsp;&nbsp;b) Adicione essa regra ao banco de dados e diga qual seria a resposta à consulta *?- predador(X)*.  

  
3. q3




  
### Referências
<a id="ref_gersting"></a> 1: GERSTING, Judith L. **Fundamentos matemáticos para a ciência da computação : matemática discreta e suas aplicações** - 7. ed. Rio de Janeiro: LTC, 2017.  
<a id="ref_sebesta"></a> 2: SEBESTA, Robert W. **Conceitos de linguagens de programação** - 9. ed. Porto Alegre : Bookman, 2011.
