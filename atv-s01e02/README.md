# Classificação de Hardware com várias CPUs

        Francisco das Chagas Peres Júnior - Engenharia da Computação

Como citado anteriormente na tarefa ‘atv-s01e01’ os sistemas distribuídos são particionados em diversos computadores e múltiplos processos ocorrem simultaneamente, ou seja, computação paralela.
Em questão de hardware, esse tipo de computação ocorre em multiprocessadores que aumentam o desempenho dos processos. Esses multiprocessadores podem ser organizados de maneiras diferentes. 

## Tipo de organização:

### Multiprocessadores:

Os processadores compartilham do mesmo barramento para memória, sendo uma única memória principal ou múltiplas memórias. Assim como as memórias, os dispositivos E/S também são compartilhados. Desse tipo temos:
-	**Multiprocessadores simétricos (SPM):** Um único SO controla todas as operações dos processadores e seus acessos a memória.
-   **NUMA:** Os processadores são organizados em blocos que seguem a organização SPM e cada bloco possui sua memória principal, caso precise solicitar parte da memória de outro bloco essa é transmitida através do barramento entre os blocos.

Nesse tipo de organização, somente um processador pode utilizar o barramento por vez (gargalo de Von Neumann), sendo assim se faz uso de memória cache para evitar esse uso constante.
Como uma cópia da memória principal, cria-se um problema de consistência entre essas memórias quando um dado ou arquivo é alterado.
Com de processadores, o uso do barramento aumenta também, dessa forma há limitação no número de processadores que se podem utilizar. A organização NUMA permite um uso maior de processadores devido a sua arquitetura, mas possui o mesmo problema.

#### Tipos de Barramento:
A fim de se evitar um bloqueio do barramento através de um barramento serial, pode-se utilizar de dois tipos de barramento:
-   **Cross-bar:** Cria-se uma matriz com os processadores e as memórias em que cada intercessão tem um comutador para levar a CPU até a memória desejada. Eleva muito o custo do sistema, o número de comutadores é igual a multiplicação do número de processadores pelo número de memórias.
-   **Rede de comutação Ômega:** Os comutadores possuem duas entradas que podem ser processadores ou comutadores e duas saídas que levam ou a memórias ou a comutadores. Nesse tipo de barramento cria-se uma rede de interconexões entre qualquer processador a qualquer unidade de memória. Pode-se ter vários roteamentos entre os comutadores até que a conexão seja estabelecida.

### Multicomputadores:
Cada processador possui uma memória própria e os processadores são conectados pelo mesmo barramento ou rede. Como exemplo:
-   **Cluester:** computadores completos (um sistema que pode funcionar sozinho) que constituem um nó do sistema e trabalham em conjunto como um único recurso computacional.
Os multiprocessadores podem ser organizados em dois tipos:
-   **Homogêneos:** Possuem configuração idêntica ou muito parecida tanto em Hardware como em software.
São em geral os que compõe os super computadores e os sistemas de clusters comerciais.
- **Heterogêneos:** Ao contrário do homogêneo as configurações do computador mudam, assim como sua largura de banda. É um sistema muito usado para projetos de pesquisa coletivos na internet e é o mais comum em sistemas distribuídos.

Em multicomputadores há uma migração de processos e dados na rede em que o sistema se encontra. Independente do nó que se inicia o processamento, parte dele pode ser transferido para outro nó fazendo um uso eficiente dos recursos.
Em redes de multicomputadores não há limitação de nós e como cada nó atua independente dos demais facilitando a manutenção do sistema. 
A grande desvantagem desse tipo de uso é que há uma dificuldade grande no compartilhamento de memória entre os nós e como nos demais sistemas com cache, há problema de consistência nos dados.

## Taxonomia de Flynn

Essa é a maneira mais comum de se organizar sistemas com processadores paralelos, sendo essas as categorias dos sistemas computacionais:
-	**Única instrução, único dado (SISD):** Uma única sequência de instruções é executada para operar em uma única memória. Sistemas com uniprocessadores se encaixam.
-	**Única instrução, múltiplos dados (SIMD):** Cada instrução é executada em um diferente conjunto de dados em espaços de memória distintos. Processadores de vetores e matrizes se encaixam.  
-	**Múltiplas instruções, único dado (MISD):** Múltiplas instruções são executadas no mesmo dado. Nenhuma máquina funciona dessa forma.
-	**Múltiplas instruções, múltiplos dados (MIMD):** Conjunto múltiplos de processadores executam instruções diferentes simultaneamente em conjuntos de dados distintos. Se encaixam os multiprocessadores e multicomputadores.

## Referências

-	TANENBAUM, Andrew S.; VAN STEEN, Maarten. **Sistemas distribuídos: Princípios e paradigmas**, 2 ed. São Paulo: Prentice Hall, 2007.
-	STALLINGS, William. **Arquitetura e organização de computadores**, 8 ed. São Paulo: Pearson Hall, 2010.
-	LOPES, Rafael Fernandes. **S01E02 - Classificação de Hardware com várias CPUs**. 2020. (16:26). Disponível em: < https://www.youtube.com/watch?v=RdEEK7JWc30>. Acesso em: 18 jun. 2020
-   CRUZ, Pedro. **Multiprocessadores & Multicomputadores**. 2017. 55 slides. Disponível em : <https://www.gta.ufrj.br/~cruz/courses/eel770/slides/17_multiproc_multicomp.pdf> Acessado em: 18 jun. 2020

