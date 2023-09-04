# Excel

O Excel é muito utilizado em estatística e análise de dados, pois envolve técnicas para coletar, organizar, 
descrever, analisar e interpretar dados provenientes de dados tabulares.

Fórmulas e metodologias de uso do Software Excel para análise de dados.

### Distribuição Binomial

#### Distribuição Binomial para o cálculo de P(X=x)
    =DISTR.BINOM(x;n;p;FALSO)


#### Distribuição Binomial para o cálculo de P(0<X<x) = P(X<x)
    =DISTR.BINOM(x;n;p;VERDADEIRO)
    
*Os resultados exibidos mostrarão a probabilidade acumulada!

### Exemplo prático:
Cada amostra de ar tem 10% de chance de conter uma certa molécula rara. Considere que as 
amostras sejam independentes com relação à presença da molécula rara. Encontre a probabilidade 
de que em 18 amostras:
- a) Exatamente 2 contenham a molécula rara. 
- b) No mínimo 4 amostras contenham a molécula rara. 
- c) De 3 a 7 amostras contenham a molécula rara. 
- d) O número médio e a variância de moléculas raras.

X: número de moléculas raras encontradas.</br>
x: 0, 1, 2, 3...,18</br>
n=18</br>
e p=0,1</br>

- a) Exatamente 2 contenham a molécula rara. → P(X=2)</br></br>

        =DISTR.BINOM(2;18;0,1;FALSO)
0,283512</br>
### Resultado: 28%</br></br>


- b) No mínimo 4 amostras contenham a molécula rara.</br></br> 
→ P(X>4)=1 – P(X<4)=1-P(X<3) = 1-[P(X=0)+P(X=1)+P(X=2)+P(X=3)]

        =DISTR.BINOM(3;18;0,1;VERDADEIRO)
  
→ 0,901803 
#### * Observe que será necessário fazer 
1-0,901803=0,098197</br>

        =1-(DISTR.BINOM(3;18;0,1;VERDADEIRO))
→ 0,098197</br>
### Resultado: 9,8%</br></br>


- c) De 3 a 7 amostras contenham a molécula rara.</br></br> 
→ P(3<X<7) = P(X=3)+ P(X=4)+ P(X=5)+ P(X=6)+ P(X=7)= 0,266031

        =DISTR.BINOM(3;18;0,1;FALSO) → 0,168007
        =DISTR.BINOM(4;18;0,1;FALSO) → 0,070003
        =DISTR.BINOM(5;18;0,1;FALSO) → 0,021779
        =DISTR.BINOM(6;18;0,1;FALSO) → 0,005243
        =DISTR.BINOM(7;18;0,1;FALSO) → 0,000999

  ##### Juntando fica:
        =DISTR.BINOM(3;18;0,1;FALSO)+DISTR.BINOM(4;18;0,1;FALSO)+DISTR.BINOM(5;18;0,1;FALSO)+DISTR.BINOM(6;18;0,1;FALSO)+DISTR.BINOM(7;18;0,1;FALSO)

Outra opção: </br>
P(3<X<7) = P(X<2) – P(X<7) = 0,266204 – 0,0001734573 = 0,2660305</br>
### Resultado: 27% </br></br>

- d) O número médio e a variância de moléculas raras.</br></br> 
        X: número de moléculas raras encontradas.</br>
        x: 0, 1, 2, 3...,18</br>
        n=18</br>
        e p=0,1</br></br>
        Média:</br>
        E(X) = np = 18x0,1=1,8</br></br>
        Variância:</br>
        σ2 = npq = 18x0,1x0,9 = 1,62</br>
        →Para o desvio padrão. 𝜎 = 𝜎</br>
        2 = 1,62 = 1,272792</br></br>

  ### Resultado: -> número médio: 1,8  -> variância de moléculas raras: 1,27

  ![image](https://github.com/area-41/Excel/assets/87396846/eb2dea34-c507-4f33-b65c-d279c93e66dc)

  [Arquivo Excel](https://github.com/area-41/Excel/blob/main/Exercicio_Distribuicao_Binomial.xlsx)




