# Conceitos e características de sistemas distribuídos

## Definição:
-	Um sistema distribuído é composto por vários computadores que interagem e se mostram como um sistema único e coerente ao usuário a fim de se prestar um serviço.

## Objetivos:
-	Compartilhamento de recursos: hardware, software e/ou dados compartilhados entre os módulos do sistema promovendo colaboração e economia.
-	Transparência da distribuição: garante a apresentação ao usuário como um único sistema, podendo ser aplicado em diversos aspectos dentro do sistema.
Para tanto, utiliza-se de Middleware que conecta os módulos do sistema em uma única camada, sendo essa a apresentada ao usuário.
-	 Abertura: O sistema deve ser regido por uma linguagem de definição de interface (IDL) para garantir um padrão de operação desse sistema distribuído.
-	Interoperabilidade: capacidade de interação entre aplicações e componentes distintos através de um padrão 
-	Portabilidade: capacidade de execução de uma aplicação em diversos sistemas sem modificação.
-	Extensibilidade: capacidade de se agregar ou substituir componentes do sistema sem afetar os demais.
Garante tolerância a falhas, facilitando a manutenção e aumentando a segurança, já que cada nó é independente.

## Dificuldades:
-	Ao se escalar um serviço é fácil cair em um ponto de gargalo que são pontos únicos de falhas.
-	Nenhum nó do sistema possui informação completa sobre o sistema e sendo assim suas ações são baseadas em informações locais.
-	Não se pode garantir que os componentes do sistema estejam sincronizados para o compartilhamento de recursos.
-	Redes WAN são tipicamente mais lentas, não são confiáveis e a comunicação se dá ponto a ponto do sistema.

## Técnicas de Escalabilidade:
-	Os problemas de escalabilidade, em geral, se apresentam como problemas de desempenho gerado pela limitação de servidores e rede, dessa forma são utilizadas técnicas para otimizar o sistema:
-	Ocultar latência: utilizar de comunicação assíncrona, ou seja, não esperar por respostas de requisição.
Para aplicações interativas é interessante trazer parte do processamento para o cliente diminuindo a espera do serviço.
-	Distribuição: dividir componentes do sistema em partes menores e espalha-las pelo sistema.
-	Replicação: aumenta a disponibilidade de recursos e equilibra a carga de acesso entre os componentes do sistema.
-	As duas últimas técnicas ajudam a disponibilizar os recursos em todo o sistema distribuído diminuindo a latência de acesso para cada nó do sistema.
-	Cache: um tipo especial de replicação na qual a replicação do recurso acontece sob demanda do cliente e é armazenada localmente.
-	As técnicas de replicação devem ser aplicadas cuidadosamente, pois geram problemas de consistência com os dados.

## Referências:
-	TANENBAUM, Andrew S.; VAN STEEN, Maarten. Sistemas distribuídos: Princípios e paradigmas, 2 ed. São Paulo: Prentice Hall, 2007,cap 1, pag. 1- 9.
-	LOPES, Rafael Fernandes. S01E01 - Caracterização de Sistemas Distribuídos. 2020. (17:04). Disponível em: < https://www.youtube.com/watch?v=cWw4wGQdXn0>. Acesso em: 16 jun. 2020
