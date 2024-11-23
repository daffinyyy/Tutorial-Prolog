# Tutorial de Prolog
- adicionar uma descrição
- adicionar uma introdução
- refazer imagens

## Sumário
1. [O que é Prolog?](#ancora1)  
2. [Instalação](#ancora2)
- [Para Windows](#ancora2-1)
- [Para Linux Ubuntu](#ancora2-2)
3. [Programando em Prolog](#ancora3)
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
Durante o tutorial usaremos o SWI Prolog, você pode usar a versão online [SWISH](https://swish.swi-prolog.org) ou seguir com a instlação da interface na sua máquina.
<a id="ancora2-1"></a>
### Para Windows
1. Acesse o link <https://www.swi-prolog.org/download/stable>  
2. No bloco "Binaries" selecione a versão que melhor se adequa à sua máquina
![opções de download](imagens/downloads.png)  
3. Selecione a caixa "I understand" e clique no link de download logo abaixo
![link de download](imagens/confirma.png)
4. Após concluir o download, vá para o arquivo e execute-o para iniciar a instalação. É recomendado adicionar o ícone à tela inicial
5. Não esqueça de reiniciar a máquina após concluir a instalação
Se precisar de mais ajuda, tente verificar um [tutorial no YouTube](https://www.youtube.com/watch?v=vnGWJxl1Cbk)

<a id="ancora2-2"></a>
### Para Linux Ubuntu  
1. Execute as seguintes linhas de código no seu terminal:  
`% sudo apt-add-repository ppa:swi-prolog/stable`  
`% sudo apt-get update`  
`% sudo apt-get install swi-prolog`  
  
<a id="ancora3"></a>
## Programando em Prolog
<a id="ancora4"></a>
### Fatos
Como dito anteriormente, fatos são proposições consideradas verdadeiras. Em Prolog elas seguem a estrutura *relação*(*itens que participam da relação*) e são precedidos por um ponto final:
- Pai(Marcos, João).  
- Nublado(hoje).  
Note que Prolog não tem semântica intrínseca, logo, o significado dos fatos depende da interpretação do programador. A relação *Pai(Marcos, João)* poderia significar que Marcos é pai de João, João é pai de Marcos ou que Marcos e João são pais. Por isso, tente ser claro ao nomear as relações.
### Regras 
Sendo um condicional, as **regras** são compostas por um antecedente, que pode ser um termo simples ou uma conjunção, e caso este seja verdadeiro, gera um consequente, que é um termo simples. Em Prolog escrevemos o consequente primeiro e atribuímos uma condição a ele, seguindo a estrutura *consequente* :- *expressão antecedente*:
-
<a id="ancora5"></a>
