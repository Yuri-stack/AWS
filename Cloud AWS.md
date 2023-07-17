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

- **EC2** - permite criar instancias computacionais, que podem ser comparadas com um computador virtual onde definiremos as configurações de hardware e vamos ser responsáveis pelo sistema operacional e toda a estrutura computacional, ficando a AWS responsável pela parte física. (**IaaS**) ** principal produto
- **Amazon EC2 Auto Scaling** - serviço que ajuda a garantir que o contratante tenha a quantidade certa de servidores virtuais (instancias) em funcionamento para lidar com a carga de trabalho do seu aplicativo de forma automática. Se a demanda aumentar ele automaticamente vai incluir novos servidores/ instancias para atender essa demanda, se a demanda cair ele vai eliminar o número excedente de servidores para manter um melhor custo para o contratante. 
- **AWS Elastic Beanstalk** - é um serviço que de tudo que é necessário para executar o seu aplicativo com segurança e eficiência na AWS, você só precisa levar o código do seu aplicativo e coloca-ló dentro desse ambiente. (**PaaS**)
- **Aws Lambda** - permite executar código sem a necessidade de provisional ou gerenciar servidores, é como um assistente que executa pequenos trechos de código (funções) em resposta a eventos específicos. ( exemplo de eventos: solicitação http, upload de um arquivo no bucket ou alteração em um banco de dados) (**PaaS**)

### Redes e entrega de conteúdo

- **Amazon VPC** - serviço que permite criar rede privada virtual na nuvem e até mesmo sub-redes com tabelas de roteamento e regras de firewall. Essa rede é isolada do resto da internet e de outras redes da AWS. (**IaaS**) ** principal produto
- **Amazon Route 53** - serviço de DNS fornecido pela AWS que permite conectar nomes de domínio a recursos na internet.  Também oferece outros recursos úteis, como o registro de recursos de  saúde dos servidores, para garantir a alta disponibilidade dos recursos  da web, e o balanceamento de carga, que distribui o tráfego entre vários servidores para melhorar o desempenho. (**SaaS**)
- Amazon CloudFront - 
- Elastic Load Balancing

### Gerenciamento e Governança

- Amazon CloudWatch ** principal produto
- AWS Auto Scaling
- AWS Truted Advisor
- AWS Organizations
- AWS Cloud Formation
- AWS Config
- AWS CloudTrail

### Banco de dados

- Amazon RDS * * principal produto
- Amazon DynamoDB

### Segurança, identidade e compliance:

- AWS Identity & Access Management - **principal produto
- AWS WAF
- AWS Shield
- AWS Artifact

### Gerenciamento de custos:

- Calculadoras
- AWS Cost
- AWS Orçamentos

### Armazenamentos:

- Amazon S3 - ** produto principal
- Amazon EBS
- S3 Glacier
- Família Snow

## Responsabilidade compartilhada

A plataforma que oferece os serviços fica responsável pela manutenção do hardware, atualizações entre outros

O contratante fica responsável pela segurança da sua parte, escolha pelos produtos e gerenciamento, por exemplo. Lembrando que quase tudo pode ser gerenciado a adaptado conforme a demanda.

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

![image-20230717170153303](C:\Users\tijac\AppData\Roaming\Typora\typora-user-images\image-20230717170153303.png)

## Escalabilidade e elasticidade

**Escalabilidade** - pode crescer de acordo com a sua necessidade de demanda, necessita de acompanhamento/ gerenciamento para entender a demanda. Aqui definimos o numero mínimo de instâncias por exemplo e esse vai ser seu ponto de partida a **escalabilidade esta no número definido como máximo de instancias que se pode atingir além do mínimo**. Exemplo: tendo definido 2 instancias como mínimo, podemos  definir que em momento de alta demanda nossa aplicação pode adicionais mais 1 instância totalizando 3 instancias no máximo. **A escalabilidade aqui seria de mais 1 instância**.

Benefícios da Escalabilidade:

- Melhorar a disponibilidade
- Obter um ambiente tolerante a falhas
- Refletir nos custos operacionais



CloudFront prática

- Criar uma distribuição
- definir o bucket
- opção cros

{
        "Version": "2008-10-17",
        "Id": "PolicyForCloudFrontPrivateContent",
        "Statement": [
            {
                "Sid": "AllowCloudFrontServicePrincipal",
                "Effect": "Allow",
                "Principal": {
                    "Service": "cloudfront.amazonaws.com"
                },
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::grupoaws2/*",
                "Condition": {
                    "StringEquals": {
                      "AWS:SourceArn": "arn:aws:cloudfront::015846532360:distribution/E12I75FIUJNJUM"
                    }
                }
            }
        ]
      }