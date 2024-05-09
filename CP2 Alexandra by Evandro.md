
Hardware Hacker
Aventuras em Criação e quebrando hardware


   Translated By Evandro




2. Dentro de três fábricas muito diferentes


É difícil entender como funciona um computador sem abri-lo e olhar seu interior. Da mesma forma, é difícil entender como os produtos são feitos sem entrar em uma fábrica e conhecer a linha. Embora muitas vezes pensemos na produção como uma etapa necessária, mas enfadonha, após a inovação, na realidade, as duas estão intimamente ligadas. Um inventor pensa uma vez num produto; uma fábrica pensa no mesmo produto todos os dias, às vezes durante anos a fio.

A importância das fábricas como centro de inovação só está a crescer na economia global conectada de hoje. A realidade é que não existe uma “fábrica da Apple” ou “fábrica da Nike”. Em vez disso, há uma série de instalações que são especialistas em processos (como fabricação de PCB ou fabricação de zíperes) que são com curadoria de marcas conhecidas. Portanto, não é incomum ver produtos de dois concorrentes operando lado a lado em linhas semelhantes em uma única instalação. Essa concentração de conhecimento específico de um domínio significa que o melhor lugar para aprender como melhorar um aspecto do seu produto é muitas vezes o mesmo lugar que faz um aspecto semelhante nos produtos de todos os outros


Alguns dos maiores insights que tive sobre como melhorar um produto vieram da observação de técnicos trabalhando em uma linha e dos truques inteligentes de otimização que eles desenvolveram depois de fazerem a mesma coisa repetidamente por tanto tempo.

Este capítulo leva você a um passeio por três
fabricas que fabricam coisas cotidianas: PCBs (em particular, os usados no Arduino), cartões de memória USB e zíperes. Ao abrir a cortina, você terá alguns insights sobre as compensações de design por trás dos produtos e como elas podem ser melhoradas. Na fábrica de PCB, descobri o segredo de como eles imprimem um mapa da Itália em alta resolução na parte de trás de cada Arduino; na fábrica de cartões de memória USB, testemunhei um estranho casamento entre técnicas de fabricação de alta e baixa tecnologia; e na fábrica de zíperes, descobri como até os produtos mais humildes podem trazer lições valiosas para designers de produtos, onde nascem os arduinos
Era julho de 2012 e já se passaram cerca de seis meses desde que minha startup anterior, a Chumby, encerrou as operações. Decidi tirar um ano de folga para resolver as coisas e riscar alguns itens da lista de desejos, um dos quais era uma viagem à Itália. Minha namorada teve a brilhante ideia de entrar em contato com a equipe do Arduino para ver se eu poderia visitar a fábrica deles em Scarmagno (isso foi anos antes da divisão Arduino/Genuino) como parte do nosso itinerário. Os membros da Officine Arduino (particularmente o diretor-gerente Davide Gomba) gentilmente reservaram um tempo de suas agendas lotadas para mostrar me em torno de sua fábrica. Eles esperaram pacientemente enquanto eu expressava meu fotógrafo interno e meu amor geral por todas as coisas de hardware, e eu definitivamente saí com muitas fotos ótimas.

Uma pequena cidade no norte da Itália, Scarmagno fica a cerca de uma hora e meia de carro a oeste de Milão, perto das fábricas da Olivetti, nos arredores de Torino. A cidade cuida de toda a fabricação de placas de circuito, preenchimento de placas e distribuição de Arduinos de marca oficial. Fiquei muito animado para ver as fábricas, e o destaque do meu passeio foi conhecer a System Elettronica, a fábrica de PCBs que fabricava os PCBs do Arduino.

Um aspecto encantador da System Elettronica é que o proprietário pintou a fábrica de verde, branco e vermelho para combinar com as cores da bandeira italiana. No chão de fábrica, vi um pouco desse espírito nos postes vermelhos e verdes que percorriam toda a extensão da instalação.

 
Mas logo parei de prestar muita atenção à decoração, pois aquele chão de fábrica também era onde pude acompanhar um novo lote de Arduino Leonardos durante todo o processo de fabricação. Veja como essas placas foram feita .

começando com uma folha de cobre
As placas Arduino Leonardo começam como enormes folhas de cobre virgem FR-4, um material feito de fibra de vidro e epóxi que a maioria dos PCBs usa como substrato, uma camada isolante e estrutural entre as camadas de cobre. As folhas tinham 1,6 mm de espessura (a espessura mais comum para uma PCB, que corresponde a 1/16 polegada), provavelmente um metro de largura e cerca de um metro e meio de comprimento.


A primeira etapa no processamento de PCBs é perfurar todos os holepads, vias (os pequenos orifícios que conectam as diferentes camadas do PCB), orifícios de montagem, slots chapeados e assim por diante. Quando uma PCB é fabricada, os furos são perfurados antespadronização


o estágio em que um produto químico de mascaramento é definido fotograficamente na folha em todos os lugares em que as placas finais precisam ter cobre, incluindo locais de vestígios, almofadas de solda e assim por diante. Alguns dos furos são usados para alinhar as máscaras que modelam os traços posteriormente no processo. A perfuração também é um processo sujo e confuso que pode danificar os padrões do circuito se eles estiverem instalados antecipadamente.


Os painéis de cobre vazios foram empilhados em três alturas, e uma furadeira CNC fez uma única passagem em todos os três, permitindo perfurar três substratos por vez.


Cada furo na placa Arduino foi perfurado mecanicamente, incluindo vias. O mesmo se aplica a qualquer PCB com furos passantes, razão pela qual a contagem de vias é um parâmetro tão importante no cálculo do custo


Observe que a furadeira específica que vi na System Elettronica era relativamente pequena. Já vi enormes plataformas de perfuração na China que agrupam (conectam mecanicamente) quatro ou seis cabeças de perfuração em uma máquina do tamanho de um caminhão, processando dezenas de painéis ao mesmo tempo, em oposição aos três painéis que esta broca poderia suportar. O raciocínio por trás dessa abordagem é que o conjunto de posicionamento robótico preciso é a parte cara de uma furadeira. A furadeira em si é barata – apenas um motor giratório para acionar a broca. Portanto, uma maneira de aumentar o rendimento é agrupar várias brocas em uma grande montagem e movê-las em conjunto. Cada furadeira individual ainda passa por sua própria pilha de painéis, mas pelo preço de um posicionador XY, você obtém de quatro a seis vezes o rendimento da furadeira que vi em minha viagem à Itália. Essas máquinas maiores perfuram com tanta rapidez e força que o solo treme a cada via perfurada, mesmo a vários metros de distância.
Depois que os painéis são perfurados, limpos e rebarbados, eles
estão prontos para a próxima etapa do processo de fabricação. aplicando o padrão PCB ao cobre
O próximo passo é aplicar umfotorresistente, um produto químico sensível à luz, ao painel e expõe um padrão. Na System Elettronica esse processo utilizou uma caixa de luz e um filme de alto contraste. Também vi imagens diretas a laser – na forma de um laser de varredura raster – usadas para aplicar um padrão a uma PCB. Os scanners a laser diretos são mais comuns em casas de protótipos de giro rápido, e a imagem de filme é mais comum em casas de produção em massa.


Após a aplicação do padrão, cada painel de placas é enviado para uma máquina para ser desenvolvido. Neste caso, a mesma máquina é utilizada para revelar o fotorresistente e a máscara de solda.


gravando os PCBs
Após o processamento e revelação das fotos, os painéis passam por uma série de banhos químicos que gravam e chapeiam o cobre.
Os painéis são agitados suavemente para frente e para trás em um banho químico para agilizar o processo de gravação. O movimento também circula o ácido usado para longe dos painéis, garantindo uma taxa de ataque mais uniforme, independentemente da quantidade de cobre a ser removida. A movimentação dos painéis através desses banhos químicos foi totalmente automatizada em Scarmagno. A automação é necessária porque os painéis devem ser tratados com uma série de banhos químicos cáusticos com exposição mínima ao oxigênio. O oxigênio pode estragar um painel em questão de segundos, portanto a transferência entre os banhos precisa ser rápida e a quantidade de tempo que um painel passa no banho deve ser consistente. Os banhos também contêm produtos químicos prejudiciais aos seres humanos, por isso é muito mais seguro para um robô fazer esse trabalho.


Uma vez que os painéis são processados nesta série de soluções, um revestimento branco e fosco (que eu suponho ser de níquel ou estanho) se desenvolve em todas as superfícies do painel não tratadas com fotorresistente, incluindo as vias e almofadas do orifício de passagem anteriormente não revestidas .


Neste ponto, a resistência e o cobre não revestido são removidos, deixando apenas o FR-4 bruto e o cobre revestido. A etapa final do processamento produz um acabamento de cobre brilhante.


aplicação de máscara de solda e serigrafia
Uma vez polido o cobre, os painéis estão prontos para omáscara de solda( uma camada protetora semelhante a laca que isola os traços de cobre abaixo e evita a formação de pontes de solda acima) eserigrafia (a tinta usada para rotular componentes, desenhar logotipos e assim por diante). Estes são aplicados em um processo muito semelhante ao dos padrões de traço, usando uma fotomáscara e uma máquina reveladora/decapante.


No caso dos Arduinos, a serigrafia é na verdade uma segunda camada da máscara de solda. Uma formulação muito específica de máscara de solda branca de filme seco foi adquirida pela equipe do Arduino para criar uma camada nítida e bonita que resolvesse a intrincada arte que você vê nas placas do Arduino – especialmente o mapa da Itália na parte traseira. Outras técnicas que vi para a produção de camadas de serigrafia incluem impressão a jato de tinta de alta resolução, que é mais adequada para casas de papelão de giro rápido e, claro, o processo homônimo de serigrafia com rodo e pintura.
Testando e finalizando as placas
Depois de todo esse processamento químico, os painéis recebem um revestimento protetor de solda de uma máquina niveladora de solda a ar quente.
Com o revestimento de solda instalado, cada placa é 100% testada. 
Cada traço tem sua continuidade e resistência medidas com um par de sondas voadoras. O processo que vi é chamadoteste de cabeça voadora(também referido comoteste de sonda voadora), e nesse tipo de configuração, vários pares de braços com sondas em forma de agulha testam a continuidade entre pares de traços em um movimento rápido de batidas. Considerando todos os traços de um Arduino Leonardo, isso é muita investigação!
Felizmente, os braços do robô se movem como um borrão, pois ele pode sondar centenas de pontos por minuto.

observação	Uma alternativa ao teste de cabeça voadora é o teste em concha, onde um conjunto de pinos pogo é colocado em um acessório que pode testar toda a placa com uma única operação mecânica. No entanto, os acessórios em formato de concha são muito trabalhosos para montar e manter e exigem religação física sempre que os arquivos Gerber que descrevem as imagens PCB são atualizados. Portanto, em volumes menores, o teste de sonda voadora é mais econômico e flexível do que o teste em concha.



Esta instalação específica apenas criou os painéis; uma fábrica diferente realmente preencheu os componentes. Em situações como essa, antes que os painéis possam ser enviados para a próxima fábrica, os PCBs individuais precisam ser roteados para que caibam dentrotecnologia de montagem em superfície (SMT)máquinas para colocar os componentes. Os painéis são novamente empilhados e processados em lote por meio de uma máquina que utiliza uma fresa para cortar e soltar as placas. Depois disso, as placas estão finalmente prontas para serem enviadas às instalações da SMT.


Estou feliz por ter feito uma viagem paralela para visitar a fábrica de PCB do Arduino. Visitei várias fábricas de PCB e cada uma delas tem características diferentes e seu próprio conjunto de truques para melhorar o rendimento, bem como limitações exclusivas que os designers precisam compensar. Também foi interessante ver o pequeno truque de usar um
camada extra de máscara de solda em vez de serigrafia para obter alta qualidade cosmética. Enquanto a resolução de uma serigrafia é limitada pela malha da barreira de seda para segurar a tinta, a máscara de solda é limitada pela qualidade da óptica e do desenvolvimento químico, proporcionando uma melhoria de ordem de magnitude na resolução e, em última análise, uma qualidade percebida mais alta. Normalmente a qualidade inferior da serigrafia é aceitável porque os usuários finais não veem as placas de circuito dentro dos computadores, mas para o Arduino, o produto finaléa placa de circuito.

onde nascem os cartões de memória USB
Vários meses depois de minha visita à fábrica do Arduino, tive a sorte de ser o palestrante principal na Linux Conference Australia (LCA) 2013. Em minha palestra, “Linux in the Flesh: Adventures Embedding Linux in Hardware”, discuti como o Linux está em todos os tipos de dispositivos que vemos todos os dias. Esta história não é sobre Linux, mas conecta a mim e, tangencialmente, ao LCA a uma fábrica.
Uma das bugigangas que recebi dos organizadores do LCA foi um pequeno cartão de memória USB com o pinguim Tux, o mascote do Linux, do lado de fora. Quando vi o dispositivo, pensei que era uma pura coincidência que, cerca de uma semana antes da conferência, eu estivesse em uma fábrica que fabricava cartões de memória USB exatamente iguais. Eu vi o processo de montagem da placa USB do início ao fim e, surpreendentemente, envolveu muito menos automação do que o processo de fabricação do Arduino.
O início de um stick USB
Os pendrives USB começam a vida como chips de memória flash simples. Antes de serem montados em PCBs, esses chips são avaliados quanto à capacidade e funcionalidade da memória.



Em uma estação de trabalho nesta fábrica, pilhas de chips flash vazios aguardavam testes e armazenamento com umcartão de sonda, que possui pinos minúsculos e posicionados com muita precisão, usados para tocar almofadas apenas um pouco mais largas do que um fio de cabelo humano na superfície de um wafer de silício. (Adoro como o trabalhador desta estação em particular usou elásticos para prender um medidor de corrente analógico à placa de sonda.)


Curiosamente, os chips que vi não foram testados de forma alguma em um ambiente de sala limpa. Os trabalhadores manuseavam os cavacos com pinças e tornos de sucção manuais e montavam manualmente os cartões de sonda em seus gabaritos.

Colocando chips manualmente em um PCB
Depois que os chips foram avaliados quanto à funcionalidade, eles foram colocados à mãonos PCBs do stick USB. Esta não é uma prática incomum; todas as instalações de wire bonding orientadas para o valor que visitei dependem da colocação manual da matriz nua.



A senhora que observei colocando o molde estava usando uma ferramenta semelhante a um pauzinho feita de bambu cortado à mão. Ainda não descobri exatamente como funciona o processo, mas meu melhor palpite é que as varas de bambu têm a energia superficial certa para aderir.


a matriz de silício, de modo que o silício grude na ponta da haste de bambu. Um ponto de cola é pré-aplicado nas placas nuas, de modo que quando o operador toca a matriz na cola, a tensão superficial da cola puxa a matriz da vara de bambu.
É estranho pensar que os chips dentro do meu pendrive foram manipulados com pauzinhos modificados.
ligando os chips ao PCB
Depois que os chips foram colocados no PCB, eles foramfio ligado à placa com uma máquina de colagem automatizada, que usa reconhecimento de imagem assistido por computador para encontrar a localização das placas de colagem (essa é parte da razão pela qual as fábricas podem se safar com a colocação manual das matrizes). A ligação de fios é o processo que conecta um circuito integrado à sua embalagem, e a máquina de ligação automatizada conecta os fios ao IC a uma velocidade insana, girando a placa de circuito o tempo todo.
Enquanto eu observava esse processo, o operador teve que retirar e substituir manualmente um fio mal colado e, em seguida, realocar o fio na máquina. Dado que esses fios são mais finos que um fio de cabelo e que as almofadas de colagem na embalagem e no CI são microscópicas, isso não foi uma tarefa fácil de destreza manual.
uma olhada mais de perto nas placas USB
Assim como a fábrica do Arduino usava painéis contendo múltiplas placas Leonardo, a fábrica de cartões de memória USB usava painéis de oito cartões USB cada. Cada stick no painel consistia em um chip de memória flash e um IC controlador que fazia a ponte entre o USB e o flash bruto, uma tarefa não trivial que inclui o gerenciamento de mapas de blocos defeituosos e correção de erros, entre outras coisas. O controlador era provavelmente uma CPU da classe 8051 rodando a algumas dezenas de MHz.


Depois de colados e testados os painéis, eles foram moldados com epóxi e depois cortados em pedaços individuais, prontos para venda.
Mas isso é o suficiente sobre a fabricação de eletrônicos; a seguir, quero mostrar um tipo diferente de chão de fábrica.

um conto de dois zíperes
Meu amigo Chris “Akiba” Wang tem uma formação semelhante à minha, exceto que em sua juventude ele era muito mais descolado: ele foi dançarino de artistas como LL Cool J e Run DMC nos anos 90. Depois de passar por uma fase trabalhando para grandes empresas de semicondutores, ele finalmente desistiu e seguiu sua paixão de projetar e fabricar seus próprios projetos de hardware. Especialista em redes sem fio de curto alcance e baixo consumo de energia (ele é coautor de um livro sobre Bluetooth de baixo consumo de energia e vende uma variante Arduino + 802.15.4 chamada “Freakduino”), ele agora.

Presta consultoria para organizações como as Nações Unidas e a Universidade Keio, administra o FreakLabs e colabora com vários artistas de dança, como o Wrecking Crew, para fornecer soluções de iluminação exclusivas e atraentes para espetáculos de palco.
Tive a sorte de apresentar Akiba à área metropolitana de
Shenzhen em uma viagem com alunos do MIT Media Lab em 2013 – a mesma viagem em que visitamos a fábrica de cartões de memória USB. Desde então, ele tem explorado cada vez mais profundamente a área. Como seu trabalho abrange as disciplinas de arte performática, wearables e eletrônica, sua rede de fábricas é bem diferente da minha, por isso sempre aprecio a oportunidade de aprender mais sobre seu mundo.
Em janeiro de 2015, Akiba me levou para visitar a fábrica de zíperes de seu amigo. Fiquei muito animado com o passeio: por mais humilde que seja o produto, sempre aprendo algo novo visitando sua fábrica. Esta fábrica era muito diferente das instalações do Arduino e do stick USB. Havia muito menos funcionários e era um fabricante altamente automatizado e integrado verticalmente. Para se ter uma ideia do que isso significa, essa instalação transformou lingotes de metal, serragem e arroz em peças de zíper.


Um processo totalmente automatizado
Entre os três materiais de entrada e o produto de saída havia uma linha de fundição sob pressão totalmente automatizada para criar os puxadores e controles deslizantes de zíper, um conjunto de copos e potes vibratórios (ou, como gosto de chamá-los, “vibrapots”) para liberar e polir os zíperes e um conjunto de máquinas para rebarbar e unir cada puxador ao seu controle deslizante. Acho que contei menos de uma dúzia de funcionários nas instalações e suponho que a capacidade deles excede em muito um milhão de zíperes por mês.
Fiquei hipnotizado pelos vibrapots* que unem os zíperes. Havia dois vibrapots: um com extratores e outro com controles deslizantes. Tanto os controles deslizantes quanto os extratores foram depositados em um trilho móvel e, enquanto eu observava esses milagres em ação, parecia que os controles deslizantes e os extratores estavam se alinhando na orientação correta por mágica. Cada um caiu em seu trilho e, no final da linha, foram pressionados juntos em um formato familiar de zíper, tudo em uma única máquina totalmente automatizada.


Quando coloquei a mão na panela, descobri que não havia nenhum agitador para provocar o movimento; Eu apenas senti uma forte vibração. Relaxei minha mão e percebi que ela começou a se mover junto com todos os outros itens da panela. Todo o pote vibrava de forma tendenciosa, de modo que os itens dentro dele tendiam a se mover em movimentos circulares. Isso empurrou os puxadores e controles deslizantes para o conjunto de trilhos, que foram moldados para aproveitar as assimetrias dos objetos para permitir que apenas as peças que saltavam no trilho na orientação correta continuassem para a próxima etapa.



um processo semiautomatizado
Apesar do alto nível de automação nesta fábrica, muitos dos trabalhadores que vi realizavam uma única operação. Eles alimentaram os extratores de um tipo diferente de zíper em um dispositivo conectado a outro vibrapot contendo controles deslizantes, enquanto o dispositivo juntava os controles deslizantes e os puxadores.
Claro, perguntei: “Por que alguns zíperes têm processos de montagem totalmente automatizados, enquanto outros são semiautomáticos?”
Acontece que a resposta é muito sutil e se resume à
forma

Uma pequena guia, quase invisível, era a diferença entre a automação total e a necessidade de um ser humano para unir milhões de controles deslizantes e extratores. Para entender o porquê, vamos revisar uma etapa crítica na operação do vibrapot. Um trabalhador gentilmente pausou o vibrapot responsável por classificar os extratores na orientação correta para o processo totalmente automático para que eu pudesse tirar uma foto da etapa principal.


Quando os puxadores contornaram o trilho, sua orientação foi aleatória: alguns voltados para a direita, outros para a esquerda. Mas a operação de união só deve inserir o controle deslizante no menor dos dois orifícios. Essa pequena aba permitiu que a gravidade fizesse com que todos os extratores pendurassem na mesma direção ao cair em um trilho à esquerda.
O design de zíper semiautomático não possui essa aba; como resultado, o design é muito simétrico para que um vibrapot alinhe o extrator. Perguntei ao proprietário da fábrica se adicionar a pequena aba economizaria esse trabalho, e ele disse que sim.
Nesse ponto, parecia extremamente óbvio para mim que todos os zíperes deveriam ter essa pequena aba, mas o designer do zíper não a teria. Mesmo que essa aba seja muito pequena, os consumidores podem sentir os solavancos sutis, e alguns percebem isso como um
 

defeito no projeto. Como resultado, o designer insistiu em uma aba perfeitamente lisa, que, portanto, não tinha nenhum recurso que permitisse a orientação automática de maneira fácil e confiável.
A ironia da escassez e da demanda
Eu gostaria de imaginar que a maioria das pessoas, depois de observar uma pessoa unindo puxadores a controles deslizantes por alguns minutos, ficaria bastante contente em sofrer um pequeno impacto na ponta do zíper para salvar outro ser humano do destino de alinhar manualmente os puxadores em controles deslizantes durante oito horas por dia. Alternativamente, suponho que um engenheiro poderia gastar inúmeras horas tentando projetar um método mais complexo para alinhar os extratores e controles deslizantes, mas há dois problemas com isso:
•	O cliente do zíper provavelmente não pagaria por esse esforço.
•	Provavelmente é mais barato pagar mão de obra não qualificada para realizar a classificação manualmente.
O dono da fábrica de zíperes já havia automatizado todo o resto nas instalações, então imagino que eles também pensaram muito sobre esse problema. Meu palpite é que a construção e a manutenção de robôs são caras; as pessoas são auto-replicantes e em grande parte auto-sustentáveis. Lembra daquele terceiro insumo da fábrica: o arroz? As peças sobressalentes de qualquer robô têm que ser mais baratas que o arroz para que o robô ganhe um lugar na fábrica.
Na realidade, porém, é muito trabalhoso explicar esse conceito
aos clientes finais; na verdade, acontece exatamente o oposto no mercado. Montar os zíperes lisos envolve mão de obra extra, então os zíperes custam mais; portanto, eles tendem a acabar em produtos de alta qualidade. Isso reforça ainda mais a noção de que zíperes realmente lisos, sem nenhuma pequena aba, devem ser o resultado de controle de qualidade e atenção aos detalhes.
Meu mundo está cheio de pequenas frustrações como essa. Por exemplo, a maioria dos clientes considera os plásticos com acabamento espelhado de qualidade superior aos plásticos com acabamento acetinado. Há
 

não há diferença funcional entre o desempenho estrutural dos dois plásticos, mas fazer algo com acabamento espelhado exige muito mais esforço. As ferramentas de moldagem por injeção devem ser cuidadosa e meticulosamente polidas e, em cada etapa da fábrica, os trabalhadores devem usar luvas brancas. Montanhas de plástico são descartadas em busca de defeitos e películas extras de plástico são colocadas sobre superfícies espelhadas para protegê-las durante o transporte.
Apesar de todo esse esforço, apesar de todo esse desperdício, qual é a primeira coisa que os usuários fazem? Eles colocaram suas impressões digitais sujas em todo o acabamento espelhado. Um minuto depois de um produto sair da caixa, todo esse esforço é desfeito. Ou pior ainda, o usuário deixa a película protetora, resultando em um efeito cosmético pior do que um acabamento acetinado.
Compare isso com o plástico com acabamento acetinado. Os acabamentos acetinados não requerem películas protetoras, são mais fáceis de manusear pelos trabalhadores e usuários, duram mais e têm rendimentos muito melhores. Nas mãos do usuário, escondem pequenos arranhões, impressões digitais e pedaços de poeira. Indiscutivelmente, o acabamento acetinado oferece uma melhor experiência ao cliente a longo prazo do que o acabamento espelhado.
Mas esse acabamento espelhado certamente fica lindo em fotos e
exibições de showroo 
