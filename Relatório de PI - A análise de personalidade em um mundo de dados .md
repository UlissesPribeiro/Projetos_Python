**Nomes:** Pedro Daniel Ferreira de Sousa (RA:11202322165), Ulisses Peres Ribeiro (RA: 11202130435\) e Rebeca Hamani Bezerra Tavares da Silveira (RA: 11202320315\)

**Grupo:** G3

**Turma:** B1, segundo Quadrimestre de 2024

**Professora:** [Denise Hideko Goya](http://www.docente.ufabc.edu.br/denise.goya)

**A análise de personalidade em um mundo de dados** 

1. **Introdução**  
   

O teste de personalidade Big Five é um método utilizado no mundo corporativo e em contextos psicológicos para avaliar a personalidade de uma pessoa, seus comportamentos, características marcantes e soft skills \[1\]. 

O teste baseia-se em cinco dimensões fundamentais e essas dimensões incluem extroversão, afabilidade, conscienciosidade, abertura e neuroticismo ou emocionalidade. Extroversão é o quanto uma pessoa é sociável, assertiva ou procura interação social. A afabilidade diz respeito ao quão cooperativa, empática ou gentil uma pessoa consegue ser. A conscienciosidade mede o quanto uma pessoa é organizada, do tipo responsável ou mesmo autodisciplinada. A abertura à experiência ou a criatividade de uma pessoa e de ter uma mente aberta, e o neuroticismo, que refere-se à tendência de uma pessoa de experimentar emoções negativas, como ansiedade, raiva e tristeza \[1\]\[2\]\[3\].

Portanto, é pertinente a análise de dados do teste Big Five realizados em uma óptica diferenciada e automatizada, ou seja, dentro de um sistema automatizado criado em python e a partir disso, solucionar questionamentos levantados advindos dos objetivos propostos.

2. **Objetivo**

O objetivo deste projeto, que envolve o teste Big Five, é identificar as 44 respostas que os colegas de classe enviaram através de um formulário, desenvolvido e estruturado pela professora, e, a partir dos resultados, identificar qual é o padrão geral de personalidade da turma, ou seja, identificar nos alunos a média dos padrões de: Extroversão, afabilidade, conscienciosidade, abertura e neuroticismo, ilustrando-os em um gráfico.

3. **Códigos que foram utilizados** 

**Descrição dos módulos do código:**

* **Variáveis Gerais (Programa principal):**

A variável “traços” refere-se a: 0 \- extroversão, 1 \- afabilidade, 2 \- conscienciosidade, 3 \- abertura e 4 \- neuroticismo.   
A variável “pessoa” é usada para identificar o contador das pessoas a serem avaliadas pelo método Big Five no código.  
A variável “soma\_total” cria uma lista que contém cinco elementos onde todos iniciam com zero, no intuito de servir como uma variável de controle que irá receber a soma da pontuação de cada traço da turma em um respectivo elemento da lista \[4\]\[5\]\[6\]\[7\].  
Por fim, “Questões” é uma lista com o traço e o polo relacionados ao questionário Big Five.

* **Laço While True (Programa principal):**

Esse laço lê as respostas dos usuários todas em uma única linha e a separa número por número. Caso a quantidade de respostas seja diferente de 44, o laço se encerra, caso contrário ele continua. Ao prosseguir o laço, são criadas 3 listas vazias para armazenar traços mais acentuados (pontuação maior que 2.5), acentuados no polo oposto (pontuação menor que 1.5) e medianos (pontuação entre 1.5 e 2.5), imprime os traços classificados junto com as pontuações formatadas e soma uma unidade ao contador pessoa a cada repetição do laço \[4\]\[5\]\[6\]\[7\]. 

* **Função Converter Resposta (converter\_resposta):**

Essa função é responsável por converter as respostas de acordo com o polo informado pelo usuário ao respectivo traço. Dentro dessa função existem dois parâmetros que são a resposta referente à pergunta do questionário e seu respectivo polo (1 para positivo e \-1 para negativo).  
Sua funcionalidade é voltada para a conversão e consequente cálculo da pontuação, de acordo com a tabela de conversão de valores. Se o polo é 1, a função retorna a resposta subtraída de 1;  caso a resposta seja \-1, o valor é ajustado subtraindo a resposta de 5 \[4\]\[5\]\[6\]\[7\].

* **Função Calcular Pontuação (calcular\_pontuacao):**

Essa função é responsável por calcular a pontuação média de cada traço específico, de acordo com os dados fornecidos e passados pela função de converter a resposta. Dentro dessa função existem dois parâmetros que são a resposta do usuário e o traço para que a pontuação seja calculada.  
Sua funcionalidade dá início à soma de acordo com o número das respostas do traço, usa a função para converter a resposta, adiciona a pontuação ajustada e aumenta “n” em uma unidade a cada repetição do laço. Ao final, calcula e retorna a média dos pontos \[4\]\[5\]\[6\]\[7\]. 

* **Cálculo da Soma e Média Geral da Turma:**

Essa parte do código é responsável por calcular e exibir a soma e a média dos cinco traços avaliados para o conjunto de respostas fornecidas pelos alunos.  
Primeiro, o código percorre a lista soma\_total, que contém a soma das pontuações de cada traço, e imprime esses valores formatados com as três casas decimais. Em seguida, calcula-se a média de cada traço dividindo a soma total por 61 que é o número de alunos, armazenando os resultados em uma lista chamada media. Por fim, essas médias também são exibidas, também formatadas com três casas decimais.

**Código utilizado para calcular todos os traços e a média de cada traço:**

**def** converter\_resposta(resposta, polo):  
    **if** polo \== 1:    
        **return** resposta \- 1  
    **else**:    
        **return** 5 \- resposta

**def** calcular\_pontuacao(respostas, traço):  
    soma \= 0  
    n \= 0  
    indice \= 0  
    **for** questão in questoes:  
        **if** questão\[0\] \== traço:  
            resposta \= respostas\[indice\]  
            polo \= questão\[1\]  
            pi \= converter\_resposta(resposta, polo)  
            soma \+= pi  
            n \+= 1  
        indice \+= 1    
    **return** soma / n

traços \= \["Extroversão", "Afabilidade", "Conscienciosidade", "Abertura", "Neuroticismo"\]  
pessoa \= 1  
soma\_total \= \[0\] \* 5  
questoes \= \[  
    \[0, 1\], \[1, \-1\], \[1, \-1\], \[2, 1\], \[0, 1\], \[2, 1\], \[4, 1\], \[1, 1\], \[3, 1\], \[4, 1\],  
    \[3, 1\], \[0, \-1\], \[3, 1\], \[4, \-1\], \[1, 1\], \[0, \-1\], \[2, \-1\], \[1, 1\], \[2, \-1\], \[2, 1\],  
    \[4, \-1\], \[2, \-1\], \[4, \-1\], \[3, \-1\], \[3, 1\], \[0, 1\], \[2, 1\], \[1, \-1\], \[0, 1\], \[1, \-1\],  
    \[2, 1\], \[2, 1\], \[3, 1\], \[4, 1\], \[3, 1\], \[4, 1\], \[0, 1\], \[2, \-1\], \[3, 1\], \[1, 1\], \[4, 1\],  
    \[0, \-1\], \[3, \-1\], \[3, 1\]  
\]

**while** **True**:  
    respostas \= \[int(i) **for** i **in** input().split() **if** i\]  
    **if** len(respostas) \< 44 or len(respostas) \> 44:  
      **break**  
    **else:**  
      print("-----------------------------------------------------")  
      print(f"Divisão em 3 faixas para a pessoa {pessoa}:")  
      mais\_acentuados \= **\[\]**  
      acentuados\_oposto \= **\[\]**  
      medianos \= **\[\]**  
      **for** i **in** range(len(traços)):  
        pontuação \= calcular\_pontuacao(respostas, i)  
        **for** j **in** range(len(soma\_total)):  
          **if** j \== i:  
            soma\_total\[j\] \+= pontuação  
        **if** pontuação \> 2.5:  
            mais\_acentuados.append((traços\[i\], pontuação))  
        **elif** pontuação \< 1.5:  
            acentuados\_oposto.append((traços\[i\], pontuação))  
        **else**:  
            medianos.append((traços\[i\], pontuação))  
      **print**(**"Traços mais acentuados (pontuação \> 2.5):"**)  
      **for** traço, pontuação **in** mais\_acentuados:  
        **print**(f"  {traço}\\**t**{pontuação:.3**f**}")  
      **print**("Traços acentuados no polo oposto (pontuação \< 1.5):")  
      **for** traço, pontuação **in** acentuados\_oposto:  
        **print**(f"  {traço}\\t{pontuação:.3**f**}")  
      **print**("Traços medianos (pontuação entre 1.5 e 2.5):")  
      **for** traço, pontuação **in** medianos:  
        **print**(f"  {traço}\\t{pontuação:.3**f**}")  
      pessoa \+= 1  
        
**print**()  
**print**("Soma de todos os traços da turma:")  
**for** i **in** range(len(traços)):  
  **for** j **in** range(len(soma\_total)):  
    **if** i \== j:  
      **print**(traços\[i\], "{:.3f}".format(soma\_total\[j\]))  
**print**()  
**print**("Média geral dos traços da turma:")  
media \= \[0\] \* 5  
**for** i **in** range(len(soma\_total)):  
  **for** j **in** range(len(media)):  
    **if** i \== j:  
      media\[j\] \= soma\_total\[i\] / 61  
**for** i **in** range(len(traços)):  
  **for** j **in** range(len(media)):  
    **if** i \== j:  
      **print**(traços\[i\], "{:.3f}".format(media\[j\]))

**Dados do Questionário**

4 3 2 4 2 3 2 4 5 4 3 2 5 3 4 2 3 4 4 4 2 4 4 4 5 4 4 2 4 2 4 2 4 3 4 3 4 3 4 3 4 2 1 3  
3 4 4 4 3 4 4 4 4 4 4 4 4 4 4 4 4 3 4 4 4 4 4 3 4 4 4 4 4 4 3 5 5 5 5 4 4 4 4 5 5 5 4 4  
4 3 4 3 4 3 4 5 2 5 3 1 5 4 5 2 1 5 4 5 1 1 5 2 5 3 5 2 2 1 5 3 5 4 5 4 2 3 5 5 5 1 4 3  
2 5 4 3 2 1 5 2 3 4 4 4 4 1 2 4 5 3 5 3 2 5 3 3 4 2 2 4 2 2 2 2 4 4 3 5 2 5 3 1 3 5 2 4  
2 4 2 5 2 4 2 5 3 1 3 4 3 5 5 3 2 4 3 3 5 2 5 5 5 2 5 1 3 1 5 5 4 2 5 1 1 2 4 2 3 3 2 3  
3 4 2 4 2 3 3 4 3 2 3 5 4 3 4 4 4 4 4 3 4 4 4 4 5 3 4 2 3 3 3 2 3 2 5 2 4 2 4 4 3 5 2 2  
2 4 4 5 2 4 3 4 5 1 5 5 3 5 5 4 4 5 4 3 4 5 4 1 5 2 5 2 2 1 4 2 5 2 5 1 2 2 5 4 5 5 4 4  
2 4 4 5 2 3 4 2 5 2 5 5 4 2 4 4 4 4 3 4 4 5 4 2 5 1 5 4 2 1 5 2 5 2 5 1 2 1 5 4 5 5 4 2  
5 1 2 4 5 5 1 5 5 1 5 3 5 5 5 3 3 5 3 5 5 2 5 1 5 4 5 1 5 1 5 5 5 2 5 1 5 3 5 5 2 1 1 5  
2 3 4 4 4 5 2 5 2 3 2 5 3 3 4 4 2 4 4 4 3 5 3 4 5 1 5 4 2 1 5 4 2 4 1 3 1 1 3 1 4 5 1 2  
4 5 4 5 2 2 4 5 3 4 3 4 4 2 5 5 4 5 4 3 4 5 4 2 5 1 5 4 3 2 4 2 4 4 3 3 2 4 5 4 5 3 1 3  
3 4 1 4 3 5 2 4 3 4 2 2 3 1 5 1 2 4 4 5 1 3 2 4 5 3 5 4 3 1 4 5 2 4 4 3 3 1 3 2 5 2 4 2  
3 2 4 2 4 4 2 5 4 2 4 3 4 3 5 3 2 5 3 4 4 3 4 2 5 3 5 1 3 1 5 1 5 2 4 2 4 3 5 4 3 3 1 4  
3 1 1 3 4 4 1 5 5 1 5 2 5 2 4 2 2 5 1 5 1 2 2 2 5 5 5 1 5 2 5 3 5 4 5 3 5 1 5 5 5 1 1 3  
3 2 1 3 1 4 2 5 3 3 4 4 3 1 5 5 3 5 3 3 1 3 1 2 5 3 5 1 2 1 2 2 5 5 4 5 2 1 5 1 5 4 2 2  
3 3 4 4 2 5 1 4 4 1 4 4 2 5 4 3 2 4 3 5 3 3 4 2 5 2 4 1 4 1 5 3 4 2 5 2 4 1 3 4 3 4 2 2  
3 4 4 5 1 4 4 4 4 4 4 4 4 1 4 5 2 4 5 5 1 3 2 4 4 1 4 2 2 1 4 3 4 4 4 4 2 4 4 4 5 4 2 4  
4 1 1 3 3 3 1 4 4 2 4 3 4 3 4 3 1 5 3 3 4 3 3 4 4 5 5 1 5 1 4 2 3 2 3 3 4 2 3 2 3 3 2 4  
5 3 2 3 2 3 4 4 3 3 4 3 3 2 4 3 1 5 4 3 2 3 2 3 5 5 5 3 5 3 4 4 3 4 3 4 5 5 4 3 5 1 2 3  
4 2 4 4 4 4 2 4 4 4 4 4 4 2 4 4 5 4 5 3 2 5 2 4 3 2 4 2 2 2 4 2 4 4 1 4 2 4 2 3 4 3 1 4  
2 4 5 5 2 4 4 4 4 4 4 5 4 2 4 4 2 4 5 3 2 3 1 4 4 1 4 3 2 1 3 3 4 4 3 4 3 4 4 3 4 4 2 4  
4 2 4 3 3 2 2 4 4 2 4 2 3 3 4 3 2 4 3 4 2 3 2 2 5 3 5 2 3 2 4 3 4 3 4 3 4 3 4 4 4 3 4 2  
2 3 2 4 2 5 3 3 2 5 3 4 4 2 4 5 3 3 3 3 1 5 1 3 5 3 4 2 2 1 4 2 2 5 3 5 2 4 2 2 5 3 3 2  
3 4 2 4 1 3 5 3 2 5 2 4 3 1 3 5 2 3 3 3 1 5 1 4 3 2 4 3 2 1 4 2 2 5 2 5 2 4 2 1 5 3 3 3  
3 2 3 4 4 5 1 5 3 1 4 4 4 4 4 3 2 5 4 4 1 2 2 2 3 2 5 1 1 1 5 3 4 4 3 3 1 2 3 4 5 4 1 4  
3 3 2 5 4 2 3 5 5 4 5 2 5 2 5 4 4 5 4 5 2 5 4 2 5 2 4 1 3 2 5 2 5 2 5 3 5 5 5 5 4 2 1 5  
3 3 2 5 4 2 3 5 5 4 5 2 5 2 5 4 4 5 4 5 3 5 4 2 5 2 5 1 3 2 5 2 5 2 5 3 5 5 5 5 4 2 1 5  
4 1 5 5 5 3 1 2 5 5 5 3 5 2 3 3 1 3 2 5 2 4 3 4 5 4 3 4 5 4 2 4 5 4 5 3 3 1 3 3 5 3 2 5  
3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3  
3 4 2 4 4 4 3 4 4 4 4 4 4 3 3 3 4 3 3 3 2 4 4 4 4 4 4 4 4 4 2 3 3 3 4 4 4 4 4 4 4 4 4 4  
3 3 4 2 4 4 5 4 2 2 4 5 5 4 2 4 5 5 5 5 4 5 5 5 5 3 5 4 3 2 2 2 3 3 3 4 5 5 5 5 4 3 5 5  
4 1 4 4 2 5 1 5 4 3 4 2 4 2 5 2 1 4 2 5 2 1 2 3 3 3 5 2 3 1 5 4 3 4 4 4 3 1 3 4 5 2 1 1  
4 1 4 4 2 4 1 5 4 3 4 2 4 2 5 2 1 3 2 5 2 1 2 3 3 4 4 1 3 1 5 4 3 4 4 4 4 1 3 4 5 2 1 1  
2 2 4 4 3 3 1 5 5 3 5 5 5 3 5 4 4 4 4 4 1 4 2 2 5 4 5 5 4 3 4 3 5 4 5 5 4 4 5 4 5 4 1 5  
2 1 2 4 1 5 1 4 3 2 4 5 3 4 4 5 2 4 5 4 5 4 5 5 5 2 5 2 4 1 4 3 3 2 4 1 4 1 4 5 3 5 2 3  
4 5 3 4 2 5 2 3 5 2 1 4 4 2 5 5 1 5 4 5 1 2 1 5 2 2 5 3 1 1 5 2 3 5 4 3 1 4 3 4 5 3 2 3  
5 5 1 4 5 2 5 3 4 5 3 4 5 4 5 5 5 5 5 3 3 5 4 5 5 4 5 5 2 1 5 5 2 5 5 5 5 5 5 5 5 1 1 5  
2 3 1 4 1 4 1 5 4 5 3 5 3 2 5 5 2 5 2 4 1 2 1 5 2 2 5 1 3 1 4 4 5 5 4 3 3 2 2 5 5 4 4 1  
2 3 1 5 1 5 1 5 3 5 3 4 3 2 5 5 4 5 3 4 1 1 1 5 2 2 5 1 3 1 4 3 5 5 3 2 3 2 3 5 5 4 4 1  
3 5 2 5 3 5 5 5 5 5 5 5 5 3 5 5 2 5 3 5 3 4 2 5 5 1 5 1 3 1 5 4 5 4 4 2 3 4 3 5 5 5 5 5  
4 4 3 3 1 2 5 5 5 2 5 3 5 3 5 5 5 5 5 4 1 5 5 2 5 4 5 4 1 2 5 3 5 4 5 4 5 3 5 4 5 4 1 1  
3 4 4 5 4 2 1 3 5 2 4 4 2 4 4 2 2 4 4 5 4 2 4 3 4 3 5 2 3 2 4 3 3 2 5 2 3 2 4 2 4 3 3 1  
4 2 4 4 5 4 2 4 4 4 4 3 2 2 4 4 1 4 5 5 1 2 4 5 4 2 4 3 3 1 4 4 4 2 4 4 4 5 2 2 5 2 4 1  
3 2 1 5 3 4 2 5 4 3 4 5 5 5 4 3 2 5 2 5 2 3 5 4 5 3 5 1 4 1 5 4 5 2 3 2 4 1 4 4 4 3 2 3  
5 1 1 4 5 5 3 5 4 2 4 1 4 2 5 2 3 5 3 3 5 1 3 4 5 5 5 2 5 1 5 5 5 3 4 1 5 2 5 4 5 1 1 2  
5 1 3 1 5 5 1 4 2 1 3 2 5 5 4 3 2 5 2 3 2 4 3 1 2 5 5 1 3 4 5 4 5 5 4 5 3 4 5 2 5 3 1 1  
4 2 2 5 3 5 3 5 4 4 5 3 4 1 5 4 1 5 3 4 1 4 4 4 4 5 5 2 5 1 5 4 5 5 5 5 5 1 4 3 5 1 1 3  
4 3 4 5 2 5 1 4 3 4 2 2 2 2 4 3 3 4 1 4 1 2 4 5 3 4 5 1 4 4 5 5 1 5 3 4 3 2 2 1 5 1 5 3  
3 4 4 4 3 4 2 3 2 3 2 5 4 3 3 4 3 4 2 4 2 4 3 3 4 2 4 3 3 2 4 3 4 4 4 2 3 2 3 2 4 4 2 3  
3 3 4 4 3 4 2 3 3 4 3 4 4 2 3 4 2 4 2 4 4 4 3 3 4 2 4 3 3 2 4 3 4 3 4 3 3 3 4 3 5 4 1 3  
5 3 5 5 2 5 3 4 3 4 3 2 1 2 4 3 3 4 1 4 2 4 4 5 4 4 4 1 3 4 5 5 2 5 2 4 2 3 1 1 5 1 5 2  
4 1 3 2 3 3 1 5 3 3 2 2 3 4 5 1 3 4 4 4 2 2 4 3 3 5 5 3 4 3 5 4 2 5 3 3 4 4 3 4 5 1 5 2  
4 2 3 3 2 4 2 4 2 2 2 4 2 3 4 5 4 4 4 3 2 3 2 3 4 2 5 3 3 2 4 2 1 4 3 3 3 4 4 4 4 3 3 3  
3 2 2 4 4 4 2 4 2 2 2 4 2 2 4 4 4 4 4 3 2 3 3 4 4 2 5 3 4 4 4 4 2 4 4 4 2 4 3 3 3 4 2 3  
2 4 1 5 2 3 3 5 3 1 4 5 3 5 5 4 2 5 3 3 5 2 4 4 5 2 5 1 2 1 5 4 4 2 5 1 2 2 5 3 4 3 2 3  
3 4 2 4 3 4 1 4 4 1 4 5 5 4 5 4 2 5 5 4 2 5 4 4 5 2 5 1 3 1 5 4 5 3 4 3 2 4 5 3 3 4 1 5  
3 3 3 3 3 3 3 2 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 2 1 3 4 5 5 3 1 5 1 3 3 3 3 4 2 3 3  
3 4 4 4 2 3 1 2 3 4 4 5 3 2 3 5 2 4 3 4 3 5 3 4 3 2 4 4 3 1 3 3 3 3 3 4 2 1 4 4 4 5 3 3  
1 4 3 3 2 2 4 4 3 2 3 5 2 3 4 4 3 4 3 3 3 3 2 3 3 1 4 3 2 1 3 4 3 2 3 2 2 3 3 4 4 4 2 2  
1 4 3 3 2 3 4 4 3 3 3 5 2 3 4 4 3 4 3 3 3 3 2 3 4 1 4 2 2 1 3 4 3 3 3 3 2 3 3 4 2 5 2 2  
3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3  
0  
Com esses dados, podemos analisar de maneira efetiva os traços de cada um, para que depois de obter os resultados, resolver a média de cada um dos 5 traços para que seja identificado o padrão geral da turma.

**Médias calculadas:**

Extroversão \- 1,834  \- Afabilidade \- 2,742 \- Conscienciosidade \- 2,505 \- Abertura \- 2,554  
Neuroticismo \- 2,244

**Código utilizado para gerar o gráfico**

import matplotlib.pyplot as plt

categorias \= \['Extroversão', 'Afabilidade', 'Conscienciosidade', 'Abertura', 'Neuroticismo'\]  
valores \= \[1.834, 2.742, 2.505, 2.554,  2.244\]  
plt.figure(figsize=(10, 6))  
plt.bar(categorias, valores, color='skyblue', edgecolor='black')  
plt.xlabel('Big Five')  
plt.ylabel('Resultados')  
plt.title('Padrão Geral de Personalidade da Turma')

plt.xticks(rotation=45, ha='right')  
plt.tight\_layout()  
plt.show()

4. **Conclusão**

	A partir dos dados coletados, foi possível traçar um perfil geral que pode explicitar, de maneira efetiva, as características predominantes dos alunos. De acordo com o gráfico, o traço dominante seria o de afabilidade (média de 2,742), o que demonstra uma maior disposição de ajudar os demais e tendência a sentir empatia pelo próximo. Essa característica está mais presente em profissionais da área da saúde, além de setores de cunho social, tais como ONG (Organizações Não Governamentais) e projetos sociais \[2\]. Em contrapartida, vemos que a extroversão é o traço menos manifestado (média de 1,834 ), que evidencia uma dificuldade maior quanto ao desenvolvimento de interações sociais em grupo, podendo implicar em complicações na atuação em cargos de liderança, por exemplo \[2\].  
	Os demais traços, conscienciosidade, abertura, neuroticismo, aparecem como os mais equilibrados, mantendo uma média próxima uma da outra, acima da média 2,000. Destarte, este fato ratifica o interesse geral por descobertas e a predisposição ao aprendizado contínuo, o que indica um perfil mais aventureiro, no entanto com ressalvas tendo em vista que pode haver certa resistência a mudanças profissionais, isso devido ao neuroticismo apontado, que, por vezes, é passível de corroborar na manifestação de instabilidade emocional, assim prejudicando o indivíduo \[2\].

5. **Responsabilidades**

**Pedro Daniel, Rebeca Hamani e Ulisses Peres \-** Todos estiveram igualmente envolvidos em todas as fases do projeto, seja no desenvolvimento do código e refinamento, na ideia inicial ou na parte escrita.

6. **Referências bibliográficas**   
 


\[1\]	SELPE, Redação. Big Five: conheça a metodologia e suas 5 dimensões. Grupo Selpe. Disponível em:\<[https://www.gruposelpe.com.br/blog/metodologia-big-](https://www.gruposelpe.com.br/blog/metodologia-big-five-conheca-sua-)

[five-conheca-sua-](https://www.gruposelpe.com.br/blog/metodologia-big-five-conheca-sua-)origem-e-as-5-dimensoes/\#:\~:text=O%20que%20é%20Big%20Five,e%20reagem%20em%20diferentes%20situações.\>. Acesso em: 24 de agosto de 2024\.

\[2\]	[D](https://www.thomas.co/pt-br/author/jayson-darby)ARBY, [Jayson](https://www.thomas.co/pt-br/author/jayson-darby). THOMAS. Quais são os traços de personalidade Big Five?. Disponível em: \<[https://www.thomas.co/pt-br/resources/type/hr-guides/quais-sao-os-](https://www.thomas.co/pt-br/resources/type/hr-guides/quais-sao-os-tracos-de-personalidade-)

[tracos-de-personalidade-](https://www.thomas.co/pt-br/resources/type/hr-guides/quais-sao-os-tracos-de-personalidade-)big-five\>. Acesso em:  24 de agosto de 2024\.

\[3\]	ANDRADE, Amanda. Big Five: o que é essa metodologia?. Mindsight. Disponível em:\<https://mindsight.com.br/big-five/.\>. Acesso em: 27 de agosto de 2024\.

\[4\] 	\<[https://moodle.ufabc.edu.br/mod/vpl/view.php?id=51545\&userid=18140](https://moodle.ufabc.edu.br/mod/vpl/view.php?id=51545&userid=18140)\>. Acesso em: 31 de agosto de 2024\.

\[5\] 	\<[https://moodle.ufabc.edu.br/mod/vpl/view.php?id=67130\&userid=18140](https://moodle.ufabc.edu.br/mod/vpl/view.php?id=67130&userid=18140)\>. Acesso em: 27 de agosto de 2024\.

\[6\] 	\<[https://moodle.ufabc.edu.br/mod/vpl/view.php?id=53035\&userid=18140](https://moodle.ufabc.edu.br/mod/vpl/view.php?id=53035&userid=18140)\>. Acesso em: 30 de agosto de 2024\.

\[7\] 	\<[https://moodle.ufabc.edu.br/mod/vpl/view.php?id=53018\&userid=18140](https://moodle.ufabc.edu.br/mod/vpl/view.php?id=53018&userid=18140)\>. Acesso em: 27 de agosto de 2024\.

