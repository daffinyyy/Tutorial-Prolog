# Tutorial de Prolog
- adicionar uma descrição
- adicionar uma introdução

## Sumário
1. [O que é Prolog?](#ancora1)  
2. [Instalação](#ancora2)
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

<a id="ancora3"></a>
## Programando em Prolog
<a id="ancora4"></a>
<a id="ancora5"></a>
