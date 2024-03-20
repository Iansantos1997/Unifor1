# UNIFOR
**Nome**: Suzani Jia Yi Wang <br>
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

#### Pseudocódigo
```
1  ALGORITMO calReajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere
3  INICIO
4  LEIA sal, prof
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal
10  SENÃO
11    sal_reaj ← 1.1 * sal
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj
14 FIM
```

#### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

## Lista de exercícios 02

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([início])-->B[/X1, X2, X3, X4/]
B-->C{{"digite quatro notas de avaliações"}}
C-->D["M=(X1+X2+X3+X4)/4"]
D-->F{{"média é de"M}}
F-->Z([fim])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO calcmédia
DECLARE X1, X2 , X3, X4, M NÚMERICO INTEIRO
INÍCIO
ESCREVA"DIGITE QUATRO NOTAS DE AVALIAÇÕES "
LEIA X1, X2, X3, X4
M<--(X1+X2+X3+X4)/4
ESCREVA"MÉDIA="M
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)


|X1|X2|X3|X4|soma| média |
|-|-|-|-|-|-|
|6|6|9|7|28|7
|7|6|4|3|20|5
|3|6|9|6|24|6

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)
```mermaid
flowchart TD
A([início ])-->B{{digite a temperatura em celsius}}
B-->C[/c,F/]
C-->D["F = (9/5 * c) + 32"]
D-->E{{"Temperatura em Fahrenheit é de"F}}
E-->Z([Fim])

```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO calctemperatura
DECLARE c, F NÚMERICO
INÍCIO
ESCREVA "digite a temperatura em Celsius"
LEIA c
F<--(9/5*c)+32
ESCREVA "Temperatura em Fahrenheit é de" F
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

|Celsius (C°)|calculo|Fahrenheit (F°)|
|-|-|-|
|75|(9/5*75)+32|135|
|85|(9/5*85)+32|153|
|55|(9/5*55)+32|99|

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite dois números: "}}
B --> C[\X1,X2\]
C --> D{{"Escolha uma das operações [+][-][*][/]: "}}
D --> E[\op\]
E --> F{"op == +"}
F --True--> G[res = X1 + X2]
G --> H{{"res"}}
F --False--> I{"op == -"}
I --True--> J[res = X1 - X2]
J --> H
I --False--> K{"op == *"}
K --True--> L[res = X1 * X2]
L --> H
K --False--> M["op == /"]
M--> N{"X2 != 0"}
N --True--> O[res = X1/X2]
O --> H
N --False--> P{{"Digite um número maior que zero"}}
P --> O
H --> Z([FIM])
```
#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO calculadora
2 DECLARE X1, X2: real
3	op: caractere
4 INÍCIO
5 ESCREVA "Digite dois números: "
6 LEIA X1, X2
7 ESCREVA "Escolha uma das operações [+][-][*][/]: "
8 LEIA op
9     CASO op == +
10    CALCULE res = X1 + X2
11      CASO op == -
        CALCULE res = X1 - X2
          CASO op == *
          CALCULE res = X1 * X2
            SENÃO OP == /
              SE X2!= 0
              CALCULE res = X1 / X2
              SENÃO ESCREVA"Digite um número maior que zero"
              CALCULE res =X1 / X2   
FIM_SE
FIM_ESCOLHA
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([início])-->B{{"digite a idade do nadador"}}
B-->C[/x/]
C-->D{5<=x<=7}
D--V-->E{{"o nadador é classificado na categoria de infantil A."}}
D--F-->G{8<=x<=10}
G--V-->H{{"o nadador é classificado na categoria de infantil B."}}
G--F-->I{11<=x<=13}
I--V-->J{{"o nadador é classificado na categoria de juvenil A."}}
I--F-->K{14<=x<=17}
K--V-->L{{"o nadador é classificado na categoria de juvenil B."}}
K--F-->M[x>18]
M-->N{{"o nadador é classificado na categoria de adulto."}}
N-->Z([FIM])
L-->Z
J-->Z
H-->Z
E-->Z
```

#### Pseudocódigo (1.0 ponto)


```
ALGORITMO classificação
DECLARE x NÚMERICO INTEIRO
INÍCIO
ESCREVA "digite a idade do nadador"
LEIA x
ESCOLHA
  CASO 5<=x<=7
  ESCREVA "o nadador é classificado na categoria de infantil A."
  CASO 8<=x<=10
  ESCREVA "o nadador é classificado na categoria de infantil B."
  CASO 11<=x<=13
  ESCREVA "o nadador é classificado na categoria de juvenil A."
  CASO 14<=x<=17
  ESCREVA "o nadador é classificado na categoria de juvenil B."
  SENÃO
  x>18
  ESCREVA "o nadador é classificado na categoria de adulto."
FIM_ESCOLHA
FIM_ALGORITIMO
```

#### Teste de mesa (0.5 ponto)

| nome | idade| comparação| categoria | 
|  --  |   -- |   --      |   --      | 
| maio |14    | 14<=14<=17|juvenil B  | 
| caio |6     |5<=6<=7    |infantil A |
|olivio|8     |8<=8<=10   |infantil B |
