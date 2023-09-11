# Cloud AWS

Computação na nuvem é o termo que utilizamos para serviços e plataformas que estarão disponíveis fora da sua máquina local, podemos aqui ter desde sistema operacionais, servidores completos com recursos de memória Ram e Processadores tudo por conta de uma empresa que estará cuidando e responsável pela parte física dessa operação. Tipo e tamanho do recurso serão escolhidos pelo contratante e o pagamento na maioria das vezes é conforme a demanda de utilização.

Temos aqui alguns serviços tais como:

- computação
- redes e entregas de conteúdos
- gerenciamento e governança
- banco de dados
- segurança, identidade e compliance
- gerenciamento de custos
- armazenamentos

## Computação

- **EC2** - permite criar instancias computacionais, que podem ser comparadas com um computador virtual onde definiremos as configurações de hardware e vamos ser responsáveis pelo sistema operacional e toda a estrutura computacional, ficando a AWS responsável pela parte física. (**IaaS**) | `aplicação`: quando se quer ter mais autonomia sobre o servidor ** principal produto

Possui famílias/ tipo de instancia para melhor atender casos e necessidades, exemplo: 

**Família A**,T,M,MAC para uso geral, servidores, homologação e repositórios de códigos. 

**Família C** para computacional, modelagem científica, servidores de jogos ou anúncios e marchine learning.

instancia **T2.@xLarge** podemos entender que **T** tipo da instancia **T**= familia **2** = geração, **xLarge** = tamanho

- **Amazon EC2 Auto Scaling** - serviço que ajuda a garantir que o contratante tenha a quantidade certa de servidores virtuais (instancias) em funcionamento para lidar com a carga de trabalho do seu aplicativo de forma automática. Se a demanda aumentar ele automaticamente vai incluir novos servidores/ instancias para atender essa demanda, se a demanda cair ele vai eliminar o número excedente de servidores para manter um melhor custo para o contratante. 
- **AWS Elastic Beanstalk** - é um serviço que serve de tudo que é necessário para executar o seu aplicativo com segurança e eficiência na AWS, você só precisa levar o código do seu aplicativo e coloca-ló dentro desse ambiente. (**PaaS**)
- **Aws Lambda** - permite executar código sem a necessidade de provisional ou gerenciar servidores, é como um assistente que executa pequenos trechos de código (funções) em resposta a eventos específicos. ( exemplo de eventos: solicitação http, upload de um arquivo no bucket ou alteração em um banco de dados) (**PaaS**)

### Redes e entrega de conteúdo

- **Amazon VPC** - serviço que permite criar rede privada virtual na nuvem e até mesmo sub-redes com tabelas de roteamento e regras de firewall. Essa rede é isolada do resto da internet e de outras redes da AWS. (**IaaS**)  | `Aplicação`: para **ter segurança aprimorada**, mantendo isolados e protegidos por acesso restrito alguns recursos - **Integração com ambiente local**, se a empresa já possui estrutura On-premise. - **Ambientes de teste**, para desenvolvedores ou equipe, podendo simular cenários sem afetar a infraestrutura. ** principal produto
- **Amazon Route 53** - serviço de DNS fornecido pela AWS que permite conectar nomes de domínio a recursos na internet.  Também oferece outros recursos úteis, como o registro de recursos de  saúde dos servidores, para garantir a alta disponibilidade dos recursos  da web, e o balanceamento de carga, que distribui o tráfego entre vários servidores para melhorar o desempenho. (**SaaS**)
- **Amazon CloudFront** - Serviço de entrega de conteúdo, acelera a entrega na web de vídeos, imagens e arquivos de página web - através de um cache e aceleração ele consegue entregar o arquivo a partir do ponto de presença mais próximo, ele ajuda a proteger o conteúdo contra ataques DDoS e outros tipos de ameaça.  Faz uso de LOCAIS de BORDA e CACHE para tratar latência. (**SaaS**)
- **Elastic Load Balancing** - Serviço que ajuda a distribuir o tráfego de rede de forma eficiente entre vários servidores ou instâncias em uma aplicação. Balanceamento de carga a solicitação de acesso a uma url vai passar por ele primeiro, Distribuição de tráfego ele distribui os acessos entre as instâncias ativas para atender o serviço e ajuda a evitar que um único servidor fique sobrecarregado, alta disponibilidade pois esta sempre acompanhando a saúde dos servidores, Elasticidade pois ele vai se adaptando automaticamente as mudanças acionando os servidores adicionais ou pausando esses conforme demanda. (**SaaS**)

### Gerenciamento e Governança

- **Amazon CloudWatch** - Um serviço da AWS que permite monitorar recursos e aplicações em nuvem em tempo real, ele coleta e rastreia métricas, logs e eventos importante que ocorrem nos serviços da AWS.  (**SaaS**) ** principal produto
- AWS Auto Scaling
- AWS Truted Advisor
- **AWS Organizations** - organiza a parte financeira da sua AWS, permite gerenciar e controlar seu ambiente de maneira centralizada. Serviço global gerencia todas as contas da AWS, centraliza o faturamento, faz agregamento de custos e gera economia com pooling de instancias reservadas. Possui camada de segurança colocando restrições nas contas com SCP.
- **AWS Cloud Formation** - é um serviço que oferece uma linguagem comum para que você possa descrever e fornecer todos os recursos de infraestrutura em um ambiente de nuvem. permite que você utilize um arquivo de texto para modelar um ambiente em nuvem (json ou Yaml por exemplo). Paga pelos recursos que configurou e não pelo Cloud formation. É uma forma de trabalho que ajuda a manter uma organização na estruturação da sua nuvem, ele oferece formas de acesso (AWS `Command Line Interface`, `Gerenciador de console AWS` ou `SDKs`) onde vc escolher um template (modelo pra gerar uma estrutura ) ou criar sua própria template - que vai gerar sua Stack (que é uma pilha de comandos para gerar suas instancias e configurações), **permite replicar uma configuração em nuvem várias vezes e ter um gerenciamento de versões e alterações**.
- **AWS Config** - Responsável por gerenciar mudanças, auxilia nas auditorias, compliance. Permite acessar, auditar e avaliar as configurações dos recursos da AWS. Restrito a uma região, configura-se regras(checklist). Notificação por Amazon SMS caso tenha sido contratado, armazena os dados em um bucket S3. 
- **AWS CloudTrail** - é um serviço que possibilita a governança, conformidade, auditoria operacional e auditoria de riscos em sua conta AWS, **diferença entre ele e o CloudWatch é que o CloudWatch tem foco em desempenho e o CloudTrail é conformidade e auditoria** (**trilha de como foi feito e quem quando e tudo em log**). Podemos criar uma trilha para acompanhar alguma ação ou ainda no Dashboard teremos uma visão geral, ele mantem 90 dias de histórico e pode-se criar a trilha para acompanhar por mais de 90 dias. Ideal para acompanhar que alterou ou deletou algum serviço.

### Banco de dados

- **Amazon RDS** - é um serviço que facilita a criação, operação e estabilidade de bancos de dados relacionais na nuvem. Permite que você escolha e configure facilmente um banco de dados relacional popular como MYSQL, PostgreSQL, Oracle, Sql Server entre outros sem necessidade de instalar ou gerenciar o software de banco de dados.  (**SaaS**) * * principal produto 
- **Amazon DynamoDB** - banco de dados não relacional, serveless ou seja em nuvem e se paga pelo que é consumido e não pelas instancias adquiridas. É escalável (ilimitado em armazenamento e taxa de transferência ), confiável tem backup continuo dos últimos 35 dias. É rápido e tem latência em microssegundos.

### Segurança, identidade e compliance:

- **AWS Identity & Access Management** - é um serviço que ajuda você a controlar e gerenciar o acesso aos recursos da sua conta na AWS, o IAM funciona como um "porteiro ele permite que seja feita as configurações para conceder ou negar permissões para usuários, grupos e até mesmo outros serviços da AWS. ** principal produto (**SaaS**)
- **AWS WAF** - é um f**irewall de aplicativos web** que permite especificar quais tráfego tem o seu acesso permitido ou bloqueado, mediante a regras pré-definidas e personalizáveis. Filtro por endereço Ip, por cabeçalhos, pelo corpo http e alguma strings uri, bloquear requisições maliciosas com **SQL injection** ou **Cross-site Scripting**, **bloquear por países**, size constraints (tamanho da requisição) e rate base-rules
- **AWS Shield** **Standard** - proteger o ambiente **contra ataque D-Dos** ( distributed Denial of Service) - varias requisições simultânea para matar a aplicação ou deixar lento o servidor. Serviço grátis.
- **AWS Shield Advanced** - você contrata o serviço com uma equipe para suporte 24x7 que investem contra esse tipo de ataque esse serviço é pago. oferece proteção extra no **Amazon EC2**, **Elastic Load Balancing**, **Amazon CloudFront**, **AWS Global Accelerator** e o **Route 53**.
- **AWS Artifact** - acordos e relatórios de conformidade. aqui encontramos AICPA SOC, ISO 27001, FedRAMP, irap, pci, nist, HIPAA, C5 e outros. 

### Gerenciamento de custos:

- **Calculadoras AWS** - é uma ferramenta gratuita que estiva os custos dos serviços da AWS que você planeja utilizar. (**Saas**)
- **AWS Cost** - ferramenta de **análise de custos** que faz parte da AWS Management Console, exibe custos detalhados por conta. São custos já ocorridos. (**SaaS**) Aqui conseguimos ver serviço, conta vinculada, região...
- **AWS Budgets ou Orçamentos** - Ferramenta que permite que você defina limites de gastos personalizados para os seus recursos. Também é possível **criar alertar para esses valores limite definidos**. (**SaaS**)

### Armazenamentos:

- **Amazon S3** - é um serviço de armazenamento de objetos da AWS que permite armazenar e recuperar grandes quantidades de dados de maneira simples e escalável. Oferece local seguro e confiável para armazenar qualquer tipo de arquivo e dados de aplicativos... nessa estrutura os arquivos são chamados objetos e eles estarão organizados em recipientes chamados bucket. | `Aplicação`:  pode ser utilizado como: **Armazenamento de arquivos**, **Acesso e compartilhamento**, **Escalabilidade** pois podemos lidar com qualquer quantidade de dados, **Backup e recuperação**. ** produto principal (**SaaS**)
- Amazon EBS
- S3 Glacier
- Família Snow

## Escalabilidade e elasticidade 

**Escalabilidade** diz respeito ao serviço que é escalável, ou seja, pode crescer de acordo com as necessidades para atende-las. Exige uma constante observação do comportamento da requisição. Ver se limites são ultrapassados com qual frequência e em que momentos. Assim podemos definir:

- número mínimo de instancias;
- número desejado de instancias;
- número disponível para escalonar de instancias
- número máximo de instancias;

Sendo o máximo o número mínimo mais o número disponível (ou seja o total de recursos que se tem a disposição). 

> Escalabilidade   =  **Amazon EC2 Auto Scaling**

Benefícios do Auto Scaling:

1. Melhorar a disponibilidade
2. Obter um ambiente tolerante a falhas - se uma instancia cair outra assume
3. Refletir nos custos operacionais

**Elasticidade** conseguir aumentar um recurso computacionais, mas sempre poder voltar ao número menor depois.

> Exemplos dessa elasticidade estão nos serviços: **Amazon EC2**, **Elastic Load Balancing**, **AWS Elastic Beanstalk** e **Amazon Elastic Cache**.

- **Escalabilidade** - aumentar/ diminuir número de instancias - servidores
- **Elasticidade** - aumentar/ diminuir recursos computacionais(memória, armazenamento...)



## Seis vantagens do uso da AWS

1. **Save Money** - não gastar com manutenção de hardware
2. **Stop Guessing** - ter maior precisão de valores com investimento em tecnologias, não é necessário planejar infraestrutura que ficará obsoleta daqui algum tempo, você pode contratar um serviço menor e ir escalando conforme a demanda e acompanhamento de consumo.
3. **Variable Expenses** - você paga pelo que é utilizado e diminui a posse, é o aluguel do recurso na nuvem. Despesas variáveis.
4. **Economies of Scale** - quanto mais empresas contratam um serviço na AWS mais esse recurso ficará com valor mais acessível pois a AWS "repassa" essa escala de maneira a melhorar o valor cobrado.
5. **Increase Speed and Aglity** - enquanto em um rede local você demora para subir um novo serviços, na nuvem isso é resolvido em poucos cliques. Temos também facilidade em montar ambientes de testes que podem ser excluídos após os testes, por exemplo.
6. **Go Global** - Sua aplicação pode ser disponibilizada em diversas regiões no globo, diminuindo a latência do serviço.

## Responsabilidade compartilhada

A plataforma que oferece os serviços fica responsável pela manutenção do hardware, atualizações entre outros

O contratante fica responsável pela segurança da sua parte, escolha pelos produtos e gerenciamento, por exemplo. Lembrando que quase tudo pode ser gerenciado a adaptado conforme a demanda. A seguir vamos retomar o assunto deixando mais nítido as responsabilidades diante de cada modelo de serviço ofertado pela AWS.

**Para o cliente** - Responsavilidade IN the cloud - ou seja na nuvem a responsabilidade do contratante é definir as tecnologias, escolher formas de criptografia, escolher tipo de rede, configurar firewall...

**Para a AWS** - responsabilidade OF the cloud - ou seja a responsabilidade da nuvem. Responsável por suportar os serviços, manter a estrutura computacional, regiões e zonas de disponibilidade.

## IaaS, SaaS e PaaS

**IaaS** - infraestrutura como serviço é o modelo computacional que entrega toda a estrutura que seria física (servidores, redes, cabeamentos, segurança de rede, Sistema operacional) - Amazon EC2 você consegue criar e gerenciar instâncias computacionais, onde nela vc terá o ambiente necessário para executar suas aplicações. Essas instâncias é um computador virtual onde pode-se definir a sua estrutura e rodar nesse ambiente suas aplicações. O objetivo desse serviço será tirar das mãos do contratante a preocupação com a parte física de um servidor. Mas aqui ainda temos como responsabilidade do contratante escolher a melhor tecnologia, serviço operacional e outros e também manter as devidas atualizações do sistema operacional e demais recursos que ele optou em utilizar em seu servidor.

**PaaS** - Plataforma como serviço, a diferença aqui é que não fica mais sob a responsabilidade do contratante atualizações de sistemas operacionais, por exemplo. O foco é na implantação e gerenciamento das suas aplicações, exemplo: AWS Elastic Beanstalk, esse é um serviço que facilita a implantação e o gerenciamento de aplicativos web e serviços na nuvem, aqui você não se preocupa com configuração de servidores, redes, balanceamento de carga e escalonamento, você só precisa se concentrar em desenvolver seu aplicativo e fazer o upload do código.

**Saas** - Software como serviço aqui o produto é completo, exemplo Gmail, você só utiliza o serviço não precisa se preocupar nem com a infla estrutura nem com a tecnologia da aplicação.

Para ficar mais nítida a diferença desses serviços veja quais são as responsabilidades de cada camada para cada um dos modelos computacionais:

- **Modelo tradicional on Premises** - Responsabilidade da empresa contratante são as camadas de:

APP | Dados | Sistema Operacional | Servidores | Armazenamento | Rede

- **Modelo IaaS** - Responsabilidade da empresa contratante são as camadas de:

APP | Dados | Sistema Operacional

- **Modelo PaaS** - Responsabilidade da empresa contratante são as camadas de:

APP | Dados

- **Modelo SaaS** - Responsabilidade da empresa contratante são as camadas de:

nada apenas utilizar o serviço

## Recurso Gerenciados

É ter como responsabilidade da AWS a infraestrutura e todos os recursos que te permitem utilizar um serviço de banco de dados.  Exemplo: precisando de um banco de dados em nuvem, podemos contratar o serviço de EC2, criar uma instancia neste e ficar responsável por toda configuração do ambiente e atualizações para o funcionamento do banco de dados ou podemos contratar apenas o serviço de banco de dados e deixar a AWS responsável por tornar este funcional e disponível.

Um recurso deixa de ser gerenciado por você e quando a outra parte inicia o gerenciamento, atualizações e manutenção do sistema operacional e a segurança.



## Infraestrutura global AWS

- **Região** é um conjunto de zona de disponibilidades onde teremos um conjunto de coleção de recursos em uma localização geográfica. Exemplo o norte da Vigínia é geralmente a região onde são implementados novos recursos em primeiro momento e depois esses recursos são replicados para outras regiões. Outro dado interessante é que no norte da Virgínia temos 6 zonas de disponibilidade. São 16 regiões.

### zonas de disponibilidade e regiões

| Localização                            | Quant. de zonas | Região         |
| -------------------------------------- | --------------- | -------------- |
| Africa (Cape Town)                     | 2               | af-south-1     |
| Hong Kong                              | 2               | ap-east-1      |
| Tóquio                                 | 2               | ap-northeast-1 |
| Asia Pacific (Seoul)                   | 2               | ap-northeast-2 |
| Asia Pacific (Osaka)                   | 2               | ap-northeast-3 |
| Mumbai                                 | 2               | ap-south-1     |
| Ásia-Pacífico (Haiderabade)            | 1               | ap-south-2     |
| Singapura                              | 2               | ap-southeast-1 |
| Sydney                                 | 2               | ap-southeast-2 |
| Ásia-Pacífico (Jacarta)                | 1               | ap-southeast-3 |
| Ásia-Pacífico (Melbourne)              | 1               | ap-southeast-4 |
| Canada (Central)                       | 4               | ca-central-1   |
| Europe (Frankfurt)                     | 2               | eu-central-1   |
| Europa (Zurique)                       | 1               | eu-central-2   |
| Estolcomo                              | 2               | eu-north-1     |
| Europa (Espanha)                       | 1               | eu-south-2     |
| Irlanda                                | 2               | eu-west-1      |
| Londres                                | 2               | eu-west-2      |
| Paris                                  | 2               | eu-west-3      |
| Oriente Médio (Emirados Árabes Unidos) | 1               | me-central-1   |
| Oriente Médio (Bahrein)                | 2               | me-south-1     |
| São Paulo                              | 2               | sa-east-1      |
| Norte da Virgínia                      | 6               | us-east-1      |
| Ohio                                   | 3               | us-east-2      |
| AWS GovCloud (Leste dos EUA)           | 1               | us-gov-east-1  |
| AWS GovCloud (Oeste dos EUA)           | 1               | us-gov-west-1  |
| Norte Califórnia                       | 3               | us-west-1      |
| Oregon                                 | 4               | us-west-2      |

- **Zona de disponibilidade estão distintos a quilômetros de distância uma das outras**, conectadas com alta velocidade, com segurança local, refrigeração e poder ser um ou mais data centers. Distância entre as zonas 100km. Uma zona de disponibilidade é um ou mais data centers distintos. Estes são conectados para ter baixa latência, auto rendimento e redundância. Essa disposição das zonas está relacionado ao conceito e Escalabilidade.

Ao contratar um serviço AWs a ideia será sempre ver qual a região mais próximo do seu usuário. Não importando muito qual a zona de disponibilidade exatamente esta seu serviço, o foco é a região estar o mais próximo possível. Dependendo de como é configurado a sua instancia quando uma zona estiver com problemas ou indisponível a outra irá assumir o serviço. Esse modelo garantiu a AWS o título de líder do IaaS - infraestrutura como serviço.

- **Edge Locations** ou **PoPs (pontos de presença) são utilizados como cache de dados** é uma infraestrutura de servidores, localizado próximo de uma zona de disponibilidade, armazena dados mais solicitados no cache para melhorar latência de uma requisição de consulta. Estão em pontos estratégicos sem cobertura pela AWS. Exemplo:  Amazon Cloud Front, que armazena o cache do seu site estático, por exemplo. Outro serviço AWS Lightsail ou AWS ElastiCache (banco de dados em memória)

## Serviços Globais e Regionais

**Serviços regionais**:

A maioria dos serviços são regionais, ou seja, se você iniciar esse serviço em uma região ele esta em um data center, se você alterar a região ele vai deixar de estar disponível naquela região.

- EC2
- AWS Lambda
- AWS Elastic Beanstalk
- Amazon EC2 Auto Scaling

**Serviços Globais**:

Serviços globais independem de uma região, você pode configurar e depois acessar de qualquer região.

- Amazon CloudFront
- Amazon Route 53
- AWS Identity & Access Management
- AWS Waf

## Planos de suporte

- **Basic** - Grátis, é oferecido a todos os clientes da AWS, tem suporte limitado, não permite abrir tickets. Acesso ao AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem) 7 itens, inclui acesso a documentação, fóruns, recursos de auto atendimento. Ideal para uso em ambientes de desenvolvimento e testes com baixas exigências de suporte.
- **Developer** - Oferece acesso ao suporte técnico por e-mail durante horário comercial. Ajuda resolver questões técnicas e problemas relacionados a serviços AWS, indicado para desenvolvedores que precisam de um pouco mais de suporte para ambientes de produção de menor escala. Custo de $29,00, nível experimentação. Acesso ao AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem) 7 itens. Abrir tickets apenas 1 pessoa. SLA até 24 horas horário comercial.
- **Business** - suporte 24x7 com tempos de resposta rápido(até 1 hora) e suporte aprimorado. Inclui um gerente de sucesso do cliente dedicado para fornecer orientação estratégica(um terceirizado). Ideal para empresas que necessitam de um suporte completo e personalizado para ambientes de produção críticos. Ticket com mais de uma pessoa, suporte por e-mail, telefone e chat, acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem), custo de $100,00, ambiente de produção.
- **Enterprise on-Ramp** - custo de $5.500,00 . acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem), suporte por telefone, e-mail e chat 24x7, ticket para mais de uma pessoa, SLA de 30min para sistema critico inativo, orientações de interoperabilidade suporte por terceiros e concierge e orientação arquitetura.
- **Enterprise** - custo de $15.000,00, para operações de missão crítica, acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem),  suporte por telefone, e-mail e chat 24x7, ticket para mais de uma pessoa, SLA de 15min para sistema critico inativo, orientações de interoperabilidade suporte por terceiros e concierge e orientação arquitetura e TAM.

Dicas para prova: 

- plano que precisa de suporte técnico, elimine o basic
- plano com até 1 hora para suporte técnico SLA - o mais barato é o business
- apenas o enterprise tem suporte técnico Tam e Concierge que ajuda a baixar os custos

## Nível gratuito AWS

A AWS oferece alguns serviços grátis, mas ainda é necessário inserir seu cartão de credito para ter uma conta na AWS, isso porque se sua ações dentro desse ambiente utilizar de recursos pagos você será cobrado. 

Tipos de oferta:

- sempre gratuito:  não expiram e estão disponíveis para todos os clientes AWS, porém tem limite de uso que se for ultrapassado gera cobranças.
- 12 meses Gratuitos: é ofertado grátis dentro do prazo de 12 meses e após isso se torna pago, a contar da data de seu cadastro inicial na AWS.
- Testes: ofertas de teste gratuito de curto prazo começam na data em que você ativa determinado serviço.

Sobre o nível gratuito: https://aws.amazon.com/pt/free/

## Interfaces de acesso AWS 

1. **AWS Management Console** - é o sistema da AWS acessado por navegador ou por celular com o aplicativo AWS Console Mobile APP.
2. **Command Line Interface (CLI)** - Prompt de linha de comandos, suporte para Linux, Power Shell..
3. **Software Development Kit (SDK)** - Este permite que se utilize um conjunto de linguagens de programação que pode ser PHP, Javascript, Java entre outras para se comunicar com a sua aplicação.

## Well-Architected

É o uso de boas práticas na nuvem. Tornando o ambiente mais seguro e econômico.

### Princípios gerais:

- parar de adivinhar a sua capacidade
- testar o produto em escala de produção
- automatizar a arquitetura para uma experimentação fácil
- permita a evolução na arquitetura
- construir a arquitetura baseado em dados - uso de ferramentas de monitoria para isso
- Melhorar através de gamedays - testes de eventos do mundo real para ver como o sistema se comporta - esta ante falhar e redundantes diante de momentos de caos
  - escalabilidade vertical e horizontal
  - recursos descartáveis nada é para sempre
  - automação: serveless IaaS auto scaling
  - Loose couple: falhar não podem cascatear não ao monolito
  - serviços não servidores: será que não tem um serviço para isso?

### 5 pilares Well-architected

1. **operational excellence**: executar e monitorar para entregar valor
2. **security**: proteger informações e sistemas
3. **reliability**: garantir que uma carga de trabalho execute sua função pretendida corretamente e de modo consistente
4. **performance efficiency**: uso eficiente de recursos e computação
5. **cost Optimization**: compreensão e controle de onde o dinheiro esta sendo gasto, ajustando os recursos e serviços

## AWS Budgets - orçamento de serviços

É um serviço que permite definir limites de gastos e receber alertas quando os custos da sua conta atingirem determinado valor. É possível criar limites mensal ou escolher uma meta personalizada, se os custos ultrapassarem esse limite, a AWS enviará um alerta para notificar por e-mail e por meio de notificação na AWs management Console.

### Como criar um alerta:

1. Pesquisar pelo serviço na busca do portal AWS
2. clicar em criar um orçamento 
3. opção Personalizado - Avançado 
4. orçamento de custos final da pagina - botão próximo 
5. preencher nome do orçamento
6. escolher opção período mensal 
7. orçamento recorrente repete todo mês 
8. Mês que vamos iniciar Junho 
9. orçamento corrigido custo = U$1,00(dólares)
10. Todos os serviços 
11. custos não combinados 
12. botão Próximo 
13. adicionar alerta
14. botão criar orçamento

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095608794394747/image.png)

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095642193625248/image.png)

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095698275680278/image.png)

![resultado esperado](https://cdn.discordapp.com/attachments/1123729724812841021/1124095862843396096/image.png)

## AWS Cost Explorer

Monta gráficos para avaliar o uso de serviços, tem uma interface fácil de usar que permite visualizar, entender e gerenciar os custos e o uso da AWS ao longo do tempo.

Dica:

**Para gerar relatório de qual serviço esta gerando maior custo, ou qual região utilizar o serviço AWS Cost Explorer, lá é possível tbm gerar arquivo CSV com os dados.**

O **AWS Cost Explorer oferece interface para visualizar entender e gerenciar os custos** e o uso da AWS ao longo do tempo, já a **AWS Budgets é para definir orçamento(quanto espero gastar)** e enviar alertas quando o uso excede o valor orçado.

![AWS Cost Explorer](https://cdn.discordapp.com/attachments/1123729724812841021/1124096036063940738/image.png)

## Calculadora de preços da AWS

É o serviço que ajuda ter uma prévia/ estimativa dos serviços antes de implementa-lós em sua conta AWS, é um simulador de custos para nuvem. Link:https://calculator.aws/#/ 

## AWS CLI

É uma forma de interagir com os serviços da AWS por linha de código que pode agilizar o desenvolvimento quando se precisa atender altas demandas com tarefas parecidas, evitando seguir um caminho de cliques.

## SDK Software Development Kit

São os kits de desenvolvimento para as tecnologias dentro do ambiente AWS, para atender demandas com Javascript, Go, .Net entre outras.

## Serviço AWS budgets - prática

1. clicar em criar um orçamento 
2. opção Personalizado - Avançado 
3. orçamento de custos 
4. final da pagina - botão próximo 
5. preencher seu nome 
6. escolher opção período mensal 
7. orçamento recorrente repete todo mês 
8. Mês que vamos iniciar Junho 
9. orçamento corrigido 
10. custo = valor que se deseja ter como limite 
11. Todos os serviços 
12. custos não combinados 
13. botão Próximo 
14. adicionar alerta
15. botão criar orçamento

Prints:

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095608794394747/image.png)

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095642193625248/image.png)

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095698275680278/image.png)

Resultado esperado:

![img](https://cdn.discordapp.com/attachments/1123729724812841021/1124095698275680278/image.png)

## IAM - dicas

O Iam é o serviço que permite gerencias usuários e grupos de usuários da sua conta, algumas dicas que devemos nos atentar:

- **Usuários possuem credenciais permanentes** e **funções possuem credenciais temporárias**
- Usuários root não devem ser compartilhados
- Use o **Least Privilege Principle** nos usuários
- Documentos Json definem as permissões de acesso
- Grupos contém outros usuários, mas não podem conter outros grupos

**Primeiro autentica - depois autoriza**

> **Usuários** - pessoa ou serviço, com credenciais permanentes. Use o Least Privilege
>
> **Grupos** - coletivo de usuários (grupos não podem conter outros grupos)
>
> **Funções** - não são permissões é um método de autenticação temporária.

## WAF - dicas

- WAF é um Firewall de aplicações web
- Atua na camada 7 -> HTTP
- Bloqueia SQL Injection (SQLi) e Cross-site scripting (XSS)
- Geo-match (bloqueio países), size constraints(limitar tamanho das requisições) e rate based-rules(limitar quantidade, requisições por segundo)

## AWS Config - dicas

- Aws Config é regional
- auxilia na auditoria das alterações dos recursos para compliance
- mantém histórico das alterações e armazena em um bucket s3 para posterior análise
- notificações de alterações são enviadas com o Amazon SNS e disponibilizadas na Dashboard painel do AWS Config
- não faz parte do plano free tier.

## AWS Organization - dicas

- é um serviço global
- permite gerenciar multiplas contas
- uma conta principal - master account
- api disponível para criação de contas
- restrição das contas usando SCP - service control police

## AWS Artifact - dicas

- Os documentos são chamados de artefatos
- os relatórios de segurança e compliance são ISO, PCI e SOC
- Os acordos de uso de serviços(agreements) são BAA e HIPAA
- são utilizados em auditorias internas e conformidade

## AWS CloudTrail -prática

1. procurar pelo serviço na caixa de pesquisa
2. clicar no botão Create Trail
3. dar um nome para a trail
4. ao criar a trail ele vai gerar um bucket s3, ele vai sugerir um nome para esse bucket, mas pode-se usar um existente, para laboratório vamos deixar ele criar
5. Events - event type  opção Management events - para ter visibilidade a eventos de chamada de API, criação de instancias, buckets| Data events são atividades de invocação de funções lambdas, get, put, delete | insights events ele analisa os volumes de chamadas para os recursos e te oferece insights - laboratório vamos marcar apenas o primeiro mesmo
6. clicar botão proximo
7. clicar em create trail
8. ele cria um bucket e o trail, ele leva uns 15 min
9. após isso lembre-se de deletar o trail para não gerar custos - apague tbm o bucket (esvaziar o mesmo primeiro)

## CloudFront prática **em desenvolvimento

- Criar uma distribuição
- definir o bucket
- opção cros

## RDS - prática

1. pesquisar pelo serviço RDS
2. verifique que não tem nenhuma instancia sendo executada 
3. clicar em `Create Data Base`
4. escolher a opção de método de criação - deixar o método Standard create (padrão)
5. escolher a engine option (mecanismo) - vamos optar pela opção Mysql
6. escolher a versão do Mysql - conversar com o cliente sempre para escolher a melhor versão 
7. **templates** escolher a opção Free tier
8. **Settings** vamos colocar o nome da instancia  no campo DB Instance Identifier 
9. em credenciais de acesso - podemos alterar o nome do usuário, mas por padrão é a Admin
10. criar a senha ou clicar em gerar uma senha, você pode escolher a opção mais viável
11. na opção **Burstable classes includes t classes** - ele não vai trazer nenhuma instancia pq estamos na opção Free tier para escolher uma instancia clique no botão "include previous generation classes", agora uma das instancias ficara disponível a menor  seria a `db.t2.micro`(vamos usar essa como treino)
12. **Storage Type** - vamos manter o `General Purpose` - tipo de disco pode ser configurado tbm conforme a necessidade
13. em **Storage autoscaling** - podemos definir se nosso tamanho de disco pode ser escalado (aumentado) conforme a demanda, e qual o tamanho máximo ele pode escalar, como se trata de um teste vamos desmarcar a opção `Enable storage` Autoscalling.
14. em **Availabillity e durability**, podemos definir o **Multi-AZ deployment** para permitir que esse banco seja replicado em outras zonas de disponibilidade caso um servidor caia outro venha a assumir por exemplo ou eliminar latência durante um backup. na versão Free Tier não temos como habilitar essa opção
15. **Connectivity/ conectividade** - vamos escolher aqui uma VPC que é sua rede privada na nuvem, essa VPC não deve ser alterada depois que o banco subir. Por isso escolhemos a nossa região e onde estão nossos clientes antes de criar o banco.
16. configurando backup - em **backup retention period** podemos definir o período de retenção de backup, exemplo os dados ficarem retidos em backup 30 dias...  para o laboratório vamos desmarcar a opção de backup automático para evitar cobranças.
17. **Monitoring** - monitorar ajuda a identificar melhorias no banco de dados - vamos deixar desmarcado para efeito de laboratório 
18. **manutenção** - ajuda a ter uma janela onde se poderá parar o banco e realizar manutenções - não vamos alterar o padrão
19. **Deletion Protection** - aqui é possível proteger o banco contra deleção, para laboratório não marcar essa opção.
20. no final da página teremos o resumo, leia confirme e clique no botão para gerar o banco de dados.
21. Caso tenha escolhido a opção de gerar a senha de acesso ao banco automaticamente, agora vc vai ver no topo da página um botão onde terá essa informação. Botão `View credential details` guarde suas informações em lugar seguro.
22. atualize a página para ver o status do banco atualizado. Aguarde até ele iniciar uma instancia.
23. Se você criou apenas para laboratório é indicado apagar o mesmo ao final. Mas antes observe se a opção Create final Snapshot esta marcada, ela indica que será feita uma cópia do banco antes de apagar e isso pode gerar custos então desmarcar essa opção.
24. Marque a caixa onde confirmamos que temos certeza que vamos continuar com a deleção e vamos sim perder as opções de backup ou copias automáticas do banco.
25. vamos digitar delete me na caixa de texto para confirmar a deleção.
26. clicar em deletar.

## Amazon DynamoDB



