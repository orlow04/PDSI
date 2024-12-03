# INF0413 - Processamento Digital de Sinais e Imagens - Scout Vision : análise de desempenho estatístico de jogadores através do Processamento de Imagens e Vídeos

Equipe:

##### 202303356 - MURILO ALVARES SILVA
##### 202300296 - MATHEUS FRANCO MEDEIROS
##### 202303337 - GABRIEL ORLOW DE OLIVEIRA SENE
##### 202303331 - DAVID O'NEIL CAMPOS FERREIRA
##### 202303328 - CARLOS EDUARDO ROCHA SOUSA

## Índice

- ### [Seção I. Introdução e revisão bibliográfica](#introdução)
- ### [Seção II. Fundamentos teóricos](#fundamentos-teóricos)
- ### [Seção III. Metodologia](#metodologia)
- ### [Seção IV. Resultados e Conclusões](#resultados-e-conclusões)
- ### [Referências](#referências)
- ### [Apêndices](#apêndices)

## Introdução

No mundo do futebol atual, possuir um conhecimento de dados e insights estatísticos de jogadores e times permite que certas equipes possam se preparar melhor e, portanto, possuir melhores resultados. O processamento de certos dados, em especial de imagens de jogos e jogadores, permite que times tenham mais possibilidades de estudo de táticas dos seus rivais, se preparando de maneira mais efetiva e gerando mais resultado. 

Para permitir isso, modelos estatísticos já foram implementados em diversos times e até em outros estados. Um belo exemplo disponível na mídia mundial é o filme MoneyBall, que conta a narrativa do time Oakland Athletics, um time de menor expressão econômico que conseguiu através de profundos estudos estatísticos realizar o 'scouting' de jogadores que gerariam o maior valor de sucesso para o time. Dessa forma, conseguiram diversas vitórias e resultados inéditos na temporada de 'playoffs', superando marcas históricas. O filme trata de eventos reais que ocorreram em 2002, com métodos que hoje podem ser considerados arcaicos. O objetivo desse relatório é apresentar uma nova proposta para essa técnica antiga de scout e análise de jogadores. 

Voltado para o exemplo do futebol, temos o time do Liverpool que usou de modelos matemáticos avançados para selecionar seu novo treinador e suas grandes compras nos anos anteriores ao seu sucesso na Champions League, maior competição do futebol europeu. Porém, o matemático que desenvolveu o modelo, Iam Graham, afirma que nunca assistiu a um jogo de futebol a fim de não apresentar algum viés na sua escolha, algo que todos humanos podem passar ao se tratar de algo passional como o esporte. Portanto, apresentamos a ideia de processar imagens de jogos através de um modelo de visão computacional, a fim de presentear esses analistas e especialistas em análises de jogadores com uma 'lente', a fim de permitir que além dos números, a performance em campo pode entrar no resultado final. 

No Brasil, já temos alguns exemplos de aplicações reais de modelos de visão computacional no processamento de imagens no contexto futebolístico. O especialista em Tecnologia do Esporte Estevão Paes Leme publicou em suas redes sociais um vídeo descrevendo o processo, que resultou em insights e análises importantes sobre a qualidade de jogadores em cobranças de pênaltis (como Gabriel Barbosa, Messi e Cristiano Ronaldo). O modelo identifica e reconhece os padrões de movimento corporal de cada atleta correspondentes a cada tipo de batida, conseguindo fazer análises preditivas de qual lado do gol será direcionado o chute antes da cobrança ser de fato efetuada. Esse case, além de poder proporcionar aos goleiros informações cruciais sobre os batedores adversários (informando qual tipo de movimento corporal indica cada tipo de batida - Cristiano Ronaldo abre o  braço esquerdo em cobranças à direita do goleiro), também gera uma nova métrica de análise quantitativa acerca da qualidade de um batedor de penâlti (Neymar, por exemplo, foi classificado como o melhor, pois tem um movimento corporal padronizado para todas suas cobranças, sendo praticamente imprevisível - a ferramenta só pôde prever o lado que a cobrança seria direcionada nos últimos instantes).

O fisiologista da equipe do Ceará, Pedro Monteiro, também tem trabalhos interessantes na área. O clube utiliza visão computacional para monitorar a ingestão de água dos atletas durante uma sessão de treino, e fornece também de forma quantitativa a qualidade da hidratação dos jogadores, possibilitando a ação antecipada dos departamentos de nutrição ou fisiologia esportiva do clube em casos de baixa hidratação, podendo então evitar lesões ou quedas de rendimento por parte dos atletas.
    
Em função de pensarmos em utilizar dados reais de jogos que ocorreram, nosso dataset consistirá de um agregado de vídeos e fotos de jogos que ocorreram no passado, de diferentes campeonatos, anos e equipes. A maioria consiste de um conjunto grande de vídeos do campeonato da primeira divisão da Alemanha (Bundesliga), contendo diversos times e inúmeras jogadas. Outro grande conjunto é uma série de fotos de jogos que ocorreram durante a última Copa do Mundo do Qatar, em 2022. Como se tratam de imagens, ao mesmo tempo que podem ser mais facilmente analisadas, podem não possuir a mesma quantidade de informação do que um vídeo. Por fim, possuem diferentes datasets especializados no tratamento de modelos de visão sobre partidas de futebol disponíveis no site Roboflow, permitindo uma validação futura para o modelo.

Para desenvolver tal modelo de visão, pensamos em seguir exemplos no mercado e utilizar do YOLO, um framework open-source que possui diversos exemplos de aplicação e de auxílio. A função desse modelo é anotar e processar os dados de imagens e vídeos de partidas de futebol. A partir desses dados, o modelo aprende a guardar e analisar os mesmos dados estatísticos que são valorizados no scout tradicional, como gols, chutes ao gol, faltas, etc. Além disso, outras métricas podem ser pensadas, principalmente aquelas que podem ser esquecidas ou ignoradas por números, como comportamento mais pessoal do jogador, jogadas de lesão e reação a adversidades possíveis em um jogo. 

A fim de validar nossos resultados, iremos integrar essa solução pensada em visão computacional com um Power BI de dados estatísticos de jogadores das principais ligas europeias. Assim, poderemos traçar métricas diferenciando os resultados da análise do modelo de visão com a abordagem mais convencional da estatística clássica de scout de jogadores.

## Fundamentos Teóricos

O trabalho é embasado em diversos fundamentos teóricos que conectam avanços em análise de dados, inteligência artificial (IA) e processamento digital de sinais e imagens ao desenvolvimento do *Scout Vision*. Este sistema utiliza modelos de visão computacional para anotar dados visuais, analisá-los e fornecer estimativas objetivas do valor de mercado de jogadores. A seguir, destacamos os principais referenciais teóricos que sustentam a abordagem do projeto.

### *Moneyball: The Art of Winning an Unfair Game* [1]

O livro de Michael Lewis é um marco na aplicação de análises quantitativas para transformar processos tradicionalmente subjetivos em avaliações mais objetivas e eficazes. A obra narra como Billy Beane, gerente geral do Oakland Athletics, desafiou métodos convencionais no beisebol ao utilizar métricas inovadoras para identificar talentos subvalorizados. Com isso, foi possível alcançar melhores resultados, mesmo com recursos limitados.

Essa abordagem fundamenta o *Scout Vision* ao reforçar a importância de questionar práticas tradicionais e aplicar tecnologias avançadas para processar dados brutos e gerar informações úteis. Assim como no beisebol, o futebol e outros esportes podem ser transformados por análises mais quantitativas e fundamentadas, permitindo uma avaliação mais precisa do desempenho dos atletas.

### "Big Data and Tactical Analysis in Elite Soccer" [2]

O artigo de Rein e Memmert explora como o big data e o aprendizado de máquina podem aprimorar a compreensão tática no futebol de elite. Os autores destacam a integração de dados técnicos, fisiológicos e táticos para descrever comportamentos complexos de equipes e jogadores. Além disso, abordam desafios na governança de dados e no acesso a tecnologias.

A relevância desse artigo para o *Scout Vision* está na aplicação de técnicas de processamento de sinais e imagens para extrair informações detalhadas sobre a performance dos atletas. O alinhamento com o uso de big data e IA reforça a capacidade do sistema de gerar insights precisos para avaliação de desempenho e cálculo do valor de mercado dos jogadores.

### "Game Plan: What AI Can Do for Football, and What Football Can Do for AI" [3]

Este artigo apresenta como a IA, combinada com aprendizado estatístico, teoria dos jogos e visão computacional, pode revolucionar a análise tática no futebol. Os autores enfatizam a importância de compreender e prever comportamentos individuais e coletivos de jogadores, além de explorar os desafios na integração de novas tecnologias.

Para o *Scout Vision*, a aplicação de modelos de visão computacional segue a lógica apresentada no artigo, permitindo a extração de dados visuais detalhados e a análise tática mais precisa. A interseção entre aprendizado de máquina, visão computacional e teoria dos jogos fornece uma base robusta para expandir as capacidades analíticas do sistema.

### "State of the Art of Sports Data Visualization" [4]

Perin e colaboradores categorizam os tipos de dados esportivos em *box score data* (estatísticas resumidas), *tracking data* (movimentos e posicionamentos em tempo real) e *meta-data* (dados contextuais). O artigo destaca a importância de desenvolver técnicas de visualização para lidar com a complexidade e heterogeneidade desses dados, além de colaborar com especialistas do domínio para garantir usabilidade prática.

Essas contribuições são cruciais para o *Scout Vision*, pois fornecem diretrizes para estruturar e interpretar dados coletados por modelos de visão computacional. A ênfase na colaboração com especialistas reforça a necessidade de validar as ferramentas desenvolvidas, garantindo que atendam às demandas práticas do esporte de elite.

### Conexão Geral

A fundamentação teórica apresentada integra os princípios de análise avançada de dados, aprendizado de máquina e visualização, aplicando-os ao contexto esportivo. Cada referência oferece insights complementares que reforçam o *Scout Vision* como uma solução inovadora para a avaliação objetiva e eficiente de atletas. A convergência entre os fundamentos teóricos e as tecnologias aplicadas torna o sistema alinhado às demandas contemporâneas do esporte e das ciências computacionais.

## Metodologia

Como mencionado anteriormente, o nosso foco de trabalho estará centrado em entender através da visão computacional, como cada jogador se comporta na partida. Portanto, estaremos como uma lupa computacional posicionada acima de cada jogada, armazenando os dados gerados e criando análises das estatísticas padrões no futebol moderno. Dessa forma, conseguiremos destrinchar os números de um jogador, sem que um analista tenha que gastar horas assistindo jogos antigos, e mais importante, sem quaisquer viés de analistas ou scouts, que podem possuir interesses pessoais ou até mesmo econômicos.

A fim de conseguirmos criar uma plataforma que possua a habilidade de proporcionar as informações que precisamos analisar, primeiro devemos procurar por dados que permitiriam nosso modelo de visão aprender como reconhecer jogadores diferentes e registrar suas ações no jogo. Para isso, podemos pensar em um benchmark para a área de visão no futebol, o dataset de jogos gravados da principal liga alemã de futebol - Bundeslisga. Com os vídeos, podemos ter uma base descente para de treinamento, que alimentará um modelo consistente do YOLOv8x, para reconhecimento dos jogadores, e do OpenCV para tracking dos jogadores no campo e da trajetória da bola.

Assim, podemos registrar todos os acontecimentos da partida para um jogador específico e anotar seus dados. Os modelos de visão são treinados para gerar esses dados, com alguns algoritmos e funções matemáticas que permitem reconhecer os elementos do futebol. Os jogadores são reconhecidos, por meio de algoritmos famosos como o K-Means, que os organizam em cluster por semelhanças na cor do uniforme e o separam por times. Outras funções vão transformar dados de reconhecimento dos jogadores, com foco nas dimensões dessa matriz gerada com os diferentes jogadores e suas posições no plano. O modelo pré-treinado do YOLO consegue, portanto, dividir nosso dataset em jogadores de ambos os times, os goleiros e os árbitros, além da bola. Em seguida, podemos associar todos a um plano novo, nosso campo. Assim, conseguimos processar de maneira efetiva os vídeos e imagens, segmentando os jogadores por time e ,através de características específicas como o número de sua camisa, atribuímos valores únicos a cada jogador. Isso permite uma análise única para cada jogador, que é identificado por um número e uma elipse no vídeo, que se assemelha muito com ambientes gamificados representativos no contexto do esporte.

Dessa maneira, após separarmos cada jogador, precisamos entender como "acompanhá-lo" pelo jogo. Para pensarmos em como tratarmos desse desafio, devemos entender que a câmera também é um objeto que se move no vídeo, e entender como controlar essa movimentação permite gerar insights valiosos. Por isso, pensamos em uma câmera que se move de maneira constante, acompanhando a bola e calculando a distância relativa que a bola percorreu. Conseguimos realizar isso através de operações sobre as caixas de reconhecimento dos jogadores e da bola. Inclusive, por meio dessa mesma métrica, de distância das caixas, conseguimos gerar um triângulo sobre a bola que irá nos auxiliar a gerar dados sobre posse de bola dos jogadores. A partir do momento que existe de maneira repetida a intersecção das classes [bola] e [jogador], consideramos um toque na bola pelo jogador. Por fim, é por meio dessas avaliações do plano de encontro entre as classes segmentados que geramos dados importantes para o jogo e para os jogadores, como controle da bola, controle de campo pelo time, posse de bola, toques na bola e velocidade da bola e dos jogadores. 

Para concluir nossa metodologia, é importante lembrar que existem maneiras diferentes para a análise de dados de visão computacional no futebol. Ao contrário da análise bruta estatística, que já é estabelecida a algumas décadas, a visão computacional para reconhecimento e geração de insights futebolísticos ainda é muito nova. Portanto, a janela para apresentar novos métodos de análise, novas ferramentas e/ou tecnologias e maior qualidade nos datasets pode melhorar o alcance final dos modelos. A escolha da metodologia desenvolvida nesse projeto foi influência de certa aula na Universidade de Uppsala, Suécia, que apresenta modelos estatísticos ligado ao futebol. Chamada " Mathematical Modelling of Football ", e ministrada pelo professor David Sumpter, autor do livro *Soccermatics*[5] referência na área. Através dessa matéria, foram gerados diversos guias para a análise e rastreamento de jogador/bola, amparados por materiais de estudo como o grupo "Friends of Tracking", que apresenta vídeos e explicações profundas para cada estatística e cada maneira de gerar tais dados. Mantendo nossa metodologia, mas aplicando novas funções com objetivos de melhorar e analisar jogadas e rastreamentos futuras, focando em dados mais volumosos como partidas completas.

## Resultados e Conclusões

## Referências

 - [1]LEWIS, Michael. Moneyball: The art of winning an unfair game. WW Norton & Company, 2004.
 - [2]REIN, Robert, and Daniel Memmert. "Big data and tactical analysis in elite soccer: future challenges and opportunities for sports science." SpringerPlus 5 (2016): 1-13.
 - [3]TUYLS, Karl, et al. "Game Plan: What AI can do for Football, and What Football can do for AI." Journal of Artificial Intelligence Research 71 (2021): 41-88.
 - [4]PERIN, Charles, et al. "State of the art of sports data visualization." Computer Graphics Forum. Vol. 37. No. 3. 2018.
 - [5]SUMPTER, David. Soccermatics: Mathematical Adventures in the Beautiful Game Pro-Edition. Bloomsbury Publishing, 2017.
  
  Datasets e GitHub de apoio:

 - https://huggingface.co/datasets/keremberke/football-object-detection?row=15
 - https://github.com/abdullahtarek/football_analysis
 - https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc
