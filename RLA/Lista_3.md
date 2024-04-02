# Unifor 
**Nome**: Ian Oliveira
**Nome de disciplina**: Raciocínio lógico algorítmico

## Q1
### fluxograma
```mermaid
flowchart TD
A([inicio])-->B{{"digite um numero"}}
B-->C[\n\]
C-->D{n>=0}
D--não-->E{{"digite um numero positivo"}}
E-->J[\n\]
J-->D
D--sim-->F{n%2==0}
F--não-->G{{"impar"}}
F--sim-->H{{"par"}}
G-->I([Fim])
H-->I([Fim])
```
### Pseodocodigo
```
ALGORITMO impar_par
DECLARE n: INTEIRO
INICIO
ESCREVA "digite um numero"
LEIA n
	SE (n<0)ENTÃO
		ESCREVA "numero negativo"
	SENÃO
		SE (n%2==0) ENTÃO
			ESCREVA "par"
		SENÃO 
			ESCREVA"impar"
		FIM_SE
	FIM_SE
FIM
```
### Teste
| entrada | negativo | positivo | impar | par | saida |
|--|--|--|--|--|--|
| 1 | nao | sim | sim | nao| impar|
| 2 |nao | sim | nao | sim| par|
| 12 |nao | sim | nao | sim| par|
| -1 | sim | nao |  | | numero negativo|

## Q2
### Fluxograma 
``` mermaid
flowchart TD
A([inicio])-->B[[i=0 até 30 passo 3]]
B-->C{{i}}
C-->B
B-->D
C-->D([Fim])
```
### Pseudocodigo
```
ALGORITMO multiplo
DECLARE i: INTEIRO
INICIO
i<--0
PARA i DE 1 ATÉ 30 PASSO 3 FAÇA
ESCREAVA i
FIM_PARA
FIM
```
### Teste
0|3|6|9|12|15|18|21|24|27|30
|-|-|-|-|-|-|-|-|-|-|-|

## Q3 
### fluxograma 
```mermaid
flowchart TD
A([Inicio])-->B{{"digite um numero "}}
B-->C[\n\]
C-->D{n!=0}
D--não-->H{{soma}}
D--sim-->E[soma=+n]
E-->F{{"digite um numero"}}
F-->G[\n\]
G-->D
H-->I([Fim])
```
### Pseudocodigo
```
ALGORITMO soma
DECLARE n, soma: NUMERICO
INICIO
ESCREVA "digite um numero"
LEIA n
soma<--0
	ENQUANTO (n!=0) FAÇA
		soma=+n
		ESCREVA "digite um numero"
		LEIA n
	FIM_ENQUANTO
	ESCREVA soma
FIM
```
### Teste
ordem|numero|n!=0|soma|saída
-|-|-|-|-
1|1|sim|1
2|2|sim|3
3|3|sim|6
4|4|sim|10
5|0|não|10|10

## Q4
### Fluxograma
```mermaid
flowchart TD
A([inicio])-->B{{"digite uma nota"}}
B-->C[\n\]
C-->D{n>=0}
D--não-->E{{soma/a}}
D--sim-->F[soma=+n]
F-->G[a=+1]
G-->H{{"digite uma nota"}}
H-->I[\n\]
I-->D
E-->J([Fim])
```
### Pseudocodigo
```
ALGORITMO media
DECLARE n, a, soma: NUMERICO
INICIO
soma <-- 0
a <-- 0
ESCREVA "digite uma nota"
LEIA n
	SE (n>=0) ENTÃO
		soma <-- +n
		a <-- +1
		ESCREVA "digite uma nota"
		LEIA n
	SENÃO 
		ESCREVA soma/a
	FIM_SE 
FIM
```
### Teste
nota | é >=0 | soma | a | saída
-|-|-|-|-
8|sim|8|1
7|sim|15|2
9|sim|24|3
5|sim|29|4
9|sim|38|5
-3|nao|38|5|7.6
