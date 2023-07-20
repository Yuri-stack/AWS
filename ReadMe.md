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
- **AWS CloudTrail** - é um serviço que possibilita a governança, conformidade, auditoria operacional e auditoria de riscos em sua conta AWS, **diferença entre ele e o CloudWatch é que o CloudWatch tem foco em desempenho e o CloudTrail é conformidade e auditoria** (trilha de como foi feito e quem quando e tudo em log). Podemos criar uma trilha para acompanhar alguma ação ou ainda no Dashboard teremos uma visão geral, ele mantem 90 dias de histórico e pode-se criar a trilha para acompanhar por mais de 90 dias.

### Banco de dados

- **Amazon RDS** - é um serviço que facilita a criação, operação e estabilidade de bancos de dados relacionais na nuvem. Permite que você escolha e configure facilmente um bando de dados relacional popular como MYSQL, PostgreSQL, Oracle, Sql Server entre outros sem necessidade de instalar ou gerenciar o software de banco de dados.  (**SaaS**) * * principal produto 
- **Amazon DynamoDB** - banco de dados não relacional, serveless ou seja em nuvem e se paga pelo que é consumido e não pelas instancias adquiridas. É escalável (ilimitado em armazenamento e taxa de transferência ), confiável tem backup continuo dos últimos 35 dias. É rápido e tem latência em microssegundos.

### Segurança, identidade e compliance:

- **AWS Identity & Access Management** - é um serviço que ajuda você a controlar e gerenciar o acesso aos recursos da sua conta na AWS, o IAM funciona como um "porteiro ele permite que seja feita as configurações para conceder ou negar permissões para usuários, grupos e até mesmo outros serviços da AWS. ** principal produto (**SaaS**)
- AWS WAF - 
- AWS Shield
- **AWS Artifact** - acordos e relatórios de conformidade. aqui encontramos AICPA SOC, ISO 27001, FedRAMP, irap, pci, nist, HIPAA, C5 e outros. 

### Gerenciamento de custos:

- **Calculadoras AWS** - é uma ferramenta gratuita que estiva os custos dos serviços da AWS que você planeja utilizar. (**Saas**)
- **AWS Cost** - ferramenta de análise de custos que faz parte da AWS Management Console, exibe custos detalhados por conta. São custos já ocorridos. (**SaaS**)
- **AWS Budgets ou Orçamentos** - Ferramenta que permite que você defina limites de gastos personalizados para os seus recursos. Também é possível criar alertar para esses valores limite definidos. (**SaaS**)

### Armazenamentos:

- **Amazon S3** - é um serviço de armazenamento de objetos da AWS que permite armazenar e recuperar grandes quantidades de dados de maneira simples e escalável. Oferece local seguro e confiável para armazenar qualquer tipo de arquivo e dados de aplicativos... nessa estrutura os arquivos são chamados objetos e eles estarão organizados em recipientes chamados bucket. | `Aplicação`:  pode ser utilizado como: **Armazenamento de arquivos**, **Acesso e compartilhamento**, **Escalabilidade** pois podemos lidar com qualquer quantidade de dados, **Backup e recuperação**. ** produto principal (**SaaS**)
- Amazon EBS
- S3 Glacier
- Família Snow

## Responsabilidade compartilhada

A plataforma que oferece os serviços fica responsável pela manutenção do hardware, atualizações entre outros

O contratante fica responsável pela segurança da sua parte, escolha pelos produtos e gerenciamento, por exemplo. Lembrando que quase tudo pode ser gerenciado a adaptado conforme a demanda. A seguir vamos retomar o assunto deixando mais nítido as responsabilidades diante de cada modelo de serviço ofertado pela AWS.

## Seis vantagens do uso da AWS

1. **Save Money** - não gastar com manutenção de hardware
2. **Stop Guessing** - ter maior precisão de valores com investimento em tecnologias, não é necessário planejar infraestrutura que ficará obsoleta daqui algum tempo, você pode contratar um serviço menor e ir escalando conforme a demanda e acompanhamento de consumo.
3. **Variable Expenses** - você paga pelo que é utilizado e diminui a posse, é o aluguel do recurso na nuvem. Despesas variáveis.
4. **Economies of Scale** - quanto mais empresas contratam um serviço na AWS mais esse recurso ficará com valor mais acessível pois a AWS "repassa" essa escala de maneira a melhorar o valor cobrado.
5. **Increase Speed and Aglity** - enquanto em um rede local você demora para subir um novo serviços, na nuvem isso é resolvido em poucos cliques. Temos também facilidade em montar ambientes de testes que podem ser excluídos após os testes, por exemplo.
6. **Go Global** - Sua aplicação pode ser disponibilizada em diversas regiões no globo, diminuindo a latência do serviço.

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

## Escalabilidade e elasticidade

**Escalabilidade** - pode crescer de acordo com a sua necessidade de demanda, necessita de acompanhamento/ gerenciamento para entender a demanda. Aqui definimos o numero mínimo de instâncias por exemplo e esse vai ser seu ponto de partida a **escalabilidade esta no número definido como máximo de instancias que se pode atingir além do mínimo**. Exemplo: tendo definido 2 instancias como mínimo, podemos  definir que em momento de alta demanda nossa aplicação pode adicionais mais 1 instância totalizando 3 instancias no máximo. **A escalabilidade aqui seria de mais 1 instância**.

Benefícios da Escalabilidade:

- Melhorar a disponibilidade
- Obter um ambiente tolerante a falhas
- Refletir nos custos operacionais

## Região e Zonas de disponibilidade

- **Região é um conjunto de data centers** em uma localização geográfica
- Cada região possui um conjunto de zonas de disponibilidade
- **Zona de disponibilidade estão distintos a quilômetros de distância uma das outras**, conectadas com alta velocidade, com segurança local, refrigeração e poder ser um ou mais data centers.
- **Edge Locations** ou **PoPs (pontos de presença) são utilizados como cache de dados** para distribuição de conteúdo. São centros de dados distribuídos globalmente em diferentes cidades ao redor do mundo. Fazem parte da rede de entregas de conteúdo da AWS conhecido como Amazon Cloud Front, pode ser entendido como mini data centers localizados perto de grandes áreas metropolitanas e guardam temporariamente dados e conteúdos populares como imagens e vídeos e arquivos estáticos.

## Planos de suporte

- **Basic** - Grátis, é oferecido a todos os clientes da AWS, tem suporte limitado, não permite abrir tickets. Acesso ao AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem) 7 itens, inclui acesso a documentação, fóruns, recursos de auto atendimento. Ideal para uso em ambientes de desenvolvimento e testes com baixas exigências de suporte.
- **Developer** - Oferece acesso ao suporte técnico por e-mail durante horário comercial. Ajuda resolver questões técnicas e problemas relacionados a serviços AWS, indicado para desenvolvedores que precisam de um pouco mais de suporte para ambientes de produção de menor escala. Custo de $29,00, nível experimentação. Acesso ao AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem) 7 itens. Abrir tickets apenas 1 pessoa. SLA até 24 horas horário comercial.
- **Business** - suporte 24x7 com tempos de resposta rápido(até 1 hora) e suporte aprimorado. Inclui um gerente de sucesso do cliente dedicado para fornecer orientação estratégica(um terceirizado). Ideal para empresas que necessitam de um suporte completo e personalizado para ambientes de produção críticos. Ticket com mais de uma pessoa, suporte por email, telefone e chat, acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem), custo de $100,00, ambiente de produção.
- **Enterprise on-Ramp** - custo de $5.500,00 . acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem), suporte por telefone, email e chat 24x7, ticket para mais de uma pessoa, SLA de 30min para sistema critico inativo, orientações de interoperabilidade suporte por terceiros e concierge e orientação arquitetura.
- **Enterprise** - custo de $15.000,00, para operações de missão crítica, acesso completo ao  AWS Trusted Advisor (serviço de recomendação e orientação para otimizar o ambiente de nuvem),  suporte por telefone, email e chat 24x7, ticket para mais de uma pessoa, SLA de 15min para sistema critico inativo, orientações de interoperabilidade suporte por terceiros e concierge e orientação arquitetura e TAM.

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
6. escolher opção periodo mensal 
7. orçamento recorrente repete todo mês 
8. Mes que vamos iniciar Junho 
9. orçamento corrigido custo = U$10,00(dolares) 
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

![AWS Cost Explorer](https://cdn.discordapp.com/attachments/1123729724812841021/1124096036063940738/image.png)

## Calculadora de preços da AWS

É o serviço que ajuda ter uma prévia/ estimativa dos serviços antes de implementa-lós em sua conta AWS, é um simulador de custos para nuvem. Link:https://calculator.aws/#/ 

## AWS CLI

É uma forma de interagir com os serviços da AWS por linha de código que pode agilizar o desenvolvimento quando se precisa atender altas demandas com tarefas parecidas, evitando seguir um caminho de cliques.

## SDK Software Development Kit

São os kits de desenvolvimento para as tecnologias dentro do ambiente AWS, para atender demandas com Javascript, Go, .Net entre outras.

## Serviço AWS budgets - prática

- clicar em criar um orçamento 
- opção Personalizado - Avançado 
- orçamento de custos 
- final da pagina - botão próximo 
- preencher seu nome 
- escolher opção período mensal 
- orçamento recorrente repete todo mês 
- Mês que vamos iniciar Junho 
- orçamento corrigido 
- custo = valor que se deseja ter como limite 
- Todos os serviços 
- custos não combinados 
- botão Próximo 
- adicionar alerta
- botão criar orçamento

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



