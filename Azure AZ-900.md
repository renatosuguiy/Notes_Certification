
#cloud #azure #certification

**Vantagens Cloud Computing
- High Availability
- Scalability: 
	- Vertical: Aumenta o numero de máquinas. 
	- Horizontal: Aumenta memória e CPU da máquina
- Agility
- Geo-Distribution
- Disaster recovery

Pq computação na nuvem é mais barato? Pq vc paga pelo que usa (pay-as-you-go)

Modelo de serviço na nuvem: SaaS, PaaS e IaaS. A responsabilidade de cada serviço muda. 
	SaaS: O clientes é responsável pelos dados, controle de acesso e dispositivos;
	PaaS: O cliente é responsável por tudo acima e tbm por identidade e infraestrutura de pasta, aplicações e controle de rede;
	IaaS: Tudo acima mais pelo sistema operacional
	On-Premise: Tudo acima mais a parte fisica do data center;

Serveless Computing: Criar aplicação sem precisar se preocupar com o hardware(infraestrutura)

Tipos de Cloud: Private Cloud(On premises), Hybrid Cloud, Public Cloud(off premises) ou várias nuvens;

Azure Arc: é um conjunto de tecnologias para gerenciar ambiente de nuvem, seja ela exclusiva na Azure, nuvem privada, hibrido ou várias nuvens. 

Solução VMware no Azure: Pode ser usada para transferir a carga de VMWare local pra Nuvem. 

## Assistente do Azure
- Dividido em 5 categorias:
	- Confiabilidade: continuidade dos aplicativos 
	- Segurança: Detectar ameaças e vunerabilidades;
	- Desempenho: Melhorar a velocidade dos aplicativos;
	- Excelencia Operacional: Eficiencia de processo e fluxo de trabalho
	- Custo: Otimizar e reduzir custos
## Azure SLA
Cada serviço da Azure tem seu próprio SLA (Service level Agreement). 

## Escalabilidade
Vertical: Aumentar ou diminuir a capacidade dos recursos;
Horizontal: Aumentar ou diminuir o numero de recursos;

## Nivel de Hierarquia de redundancia fisica:
Geografia: Pais - Formada por várias regiões
Região: Uma ou mais por localização
Zona de disponibilidade: Tem pelo menos 3 por região 

## Precificação:  
Preço por produto
Calculadora de preço
TCO = Total cost Ownership

## Tipo de uso no preço: 
### VM
- Pay-as-you-go: Maior custo
- Reserved Virtual Machine Instances: Preço fixo, preço médio
- Spot Pricing: Preço mais baixo, mas aplicação pode ser interrompida


## Subscriptions
Container lógico onde serão provisionadas os recursos da Azure. Uma conta azure pode ter várias subscriptions.
### Resource group
Nível abaixo dos subscriptions, onde serão salvos os recursos.

## Azure Cost Management
É gratis e disponível para verificar todos os custos por billing account (unico dono) e subscriptions

### Support ordenada por custo
Basic: Gratis
Developer
Standard
Professional Direct

## Azure Cloud Shell
Pode automatizar os processos por scripts. Pode fazer local ou remoto. 
"az" é a base do comando da azure.

Azure Power Shell
Azure CLI



## Compute Services

- Azure Virtual Machines - IaaS: O cliente determina o Tamanho (ram, processador), Disco e Rede
	- Conjuntos de escala de máquina virtual: VMs idênticas para balanceamento de carga.
	- Conjuntos de disponibilidade de máquina virtual: Agrupa as VMs de duas maneiras: domínio de atualização e domínio de falha
	- Os conjuntos não tem custo, só paga pelas VMs
	- Área de trabalho Virtual do azure: Windows na nuvem
- Azure App  - para aplicações web (API REST, pagina web), PaaS. Pode armazenar container.
	- Aplicativos Web;
	- Aplicativos de API;
	- WebJobs;
	- Aplicativos Móveis;
- Azure Container Instances - sem orquestrador: Vantagens. em Portabilidade de Performance. PaaS
- Azure Kubernetes (AKS) - orquestração dos conteiners. Paga pelo poder computacional 
- Windows Virtual Desktop
- Azure Function - Serveless. Pode configurar triggers para ativar as funções. Podem ser com estado ou sem estado (padrão). Sem estado, a aplicação é reiniciada toda vez que é executada. Com estado, um contexto é passado para a aplicação. 

## Networking
- Virtual Network (VNET):
	- Address space (IP): 5 ips reservados. x.x.x.0: endereço de rede. x.x.x.1: Reservado pelo Azure para o gateway padrão. x.x.x.2 e x.x.x.3: reservado pelo Azure para mapear os IPs de DNS do Azure para o espaço da VNET. x.x.x.255: endereço de broadcast
	- Subnets
	- Regions: Redes diferentes por regiões
	- Subscription
- Load Balancer: Tem healthy check. Camada 4 OSI. Por IP
	- Publico 
	- Privado
- VPN Gateway: Ligar rede onpremise para a nuvem. Site to Site, multi site. Pode ligar vnets da azure. Point to Site. 
- Application Gateway: Camada 7 (OSI). Pode balancear por URL, HTTP e HTTPS
- ExpressRoute: Não vai pelo internet publica.  Cabo direto entre azure e empresa
- Content Delivery Network(CDN): Forma de cache, pode usar POP para melhorar a entrega de conteúdo. 
- NSG: Network Security Group

# Storage
- Blob: Binary Large Object. Armazenar grande quantidade de dados não estruturados. Armazena em containers
- Disk: Armazenamento em disco fisico. Usado para máquinas virtuais 
	- Ultra Disks
	- Premiun Solid-state Drives (SSD)
	- Standard SSDs
	- Standard Hard Disk Drives (HDD)
- File: File server para compartilhar arquivos. Usa dois standards: Server Message Block (SMB) ou Network File System (NFS)
- Archive: Optimizado para gravar arquivos que raramente são acessados e armazenados por, pelo menos, 180 dias. Mais demorado para recuperar arquivos e mais caro. Pode criar life cycle para alterar os arquivos entre os tipos.  
- NoSQL
- Queue storage
## Redundancia
- LRS (armazenamento com redundância local). Protege de falhas em unidade e rack do servidor. 
- Armazenamento com redundância geográfica (GRS)
- RA-GRS (armazenamento com redundância geográfica com acesso de leitura)
- ZRS (armazenamento com redundância de zona). Replicado em um unico país. 
- Armazenamento com redundância de zona geográfica (GZRS). Armazenar em regiões separadas por centenas de km. Organizados por pares de zonas. 
- RA-GZRS (armazenamento com redundância de zona geográfica com acesso de leitura)

# DataBases

- Cosmos DB: NoSQL da AZURE (PaaS). Multi Região. Global Distribution. Precisa criar um container dentro dele para armazenar os dados. 
- Azure SQL: SQL Server
	- Azure SQL Database:  Totalmente gerenciada
	- Azure SQL Managed Instance: Parcialmente gerenciada. Ideal para migração. 
	- SQL Server on Azure VMs: Tem acesso ao sistema operacional 
- MySQL
- PostgreSQL: precisa definir infra do servidor. 
	- Single Server
	- Flexible Server
	- Hyperscale: Alta performance 
- Database Migration Services: Transportar dados do premise para a nuvem
	- Data Migration Assistance: A ferramenta em si. 
- Data Box => Transferir dados maiores de 40Tb. usando um dispositivo fisico. 
- AzCopy: Para mover pequenos arquivos Blob para a azure por linha de comando
- Gerenciador de Armazenamento do Azure: Interface gráfica para o AzCopy
- Sincronização de Arquivos do Azure: Sincroniza os arquivos bidirecionalmente

# Azure Solutions
- Internet of Things
	- IoT Central: Plataforma para gerenciar as aplicações 
	- HUB IoT: Gerenciar os dispositivos conectados
- Big Data:
	- Azure Data Lake Analytics
	- Machine Learning
		- MLOps: Treinar os modelos manualmente
		- Cognitive Services: Serviço pre prontos
		- Bot Services: 
- DevOps
	- Azure Boards
	- Azure Pipelines 
	- Azure Repos
	- Azure test Plans
	- Azure Artifacts
# Segurança
- Defense in Depth: Defesa em camadas. Várias camadas de segurança, mecanismos de segurança. Confiabilidade, integridade e disponibilidades
- Security Azure Firewall: Firewall Virtualizado.  Proteger informações internas e proteger acessos aos dados on premise, segregando o tráfego
- Network Security Groups (NSG): Groups de segurança. segurança na camada de rede, porta e protocolo. Tem regras de entrada e saída
- Azure DDoS Protection. Usa a infra da Azure proteger. O Basic todos serviços tem, o standard tem custo. 
- Azure Defender: Prove alertas de segurança para VM, SQL, Containers, WEB APP, rede, entre outros. 
- Azure Security Center. Serviço de gerenciamento de segurança. Mostra Secure score, Azure Defender, Regulatory Compliance e Inventory
- Azure Key Vault: Para armazenar senhas, certificados e segredos. Standard é virtual e o Premium inclui proteção física 
- Azure Information Protection: AIP. Classifica informações. Compartilhar informações de forma segura.
- Advance Threat Protection: Integrado no AD, Azure Monitor Logs e Azure SEcurity Center. 
- Azure Sentinel: é um SIEM, security information event manager. Coleta, Detecta, investiga e informa sobre ameaças
- Azure Dedicated Hosts: Host dedicado para uma subscrição . 

## Serviços de Identidade / Compliance

- Azure Active Directory ou Microsoft Entra ID: Diferente do AD. Evolução do AD. Pode ser usado na nuvem e on premise
- Single Sign-On: Usuário único para vários serviços. 
- Multi-Factor authentication:  Autenticação em dois fatores. 
- Azure Policy: Verificar se a conta azure está atendendo as políticas padrões. 
- Azure RBAC (role-based access control): Serve para autorizar usuários para certos serviços. 
- Azure Monitor = Cloud Watch(AWS): Centralizar em um lugar o que está acontecendo no seu ambiente. Tem que ser habilitado no serviço que vai ser criado. Sem custo
- Azure Health: Informa sobra a saude dos recursos da nuvem. Não tem custo. 
- Compliance: Todas as normas para consulta. 
- Microsoft Entra Connect: Conecta o AD local com o Microsoft Entra ID
-  Microsoft Entra Domain Services: Permite executar na nuvem aplicativos herdados que não usam métodos de autenticação modernos.  
- Entrada sem senha: Configura o dispositivo como seguro. Usado o Microsoft Authenticator para garantir segurança. 
- FIDO2: Chave padrão
- Identidades Externas do Azure:
	- Colaboração B2B: Empresa externa usa o método de identificação necessária
	- Conexão direto B2B: Usa o Canal Teams diretamente com a empresa externa
	- Microsoft Entra B2C: Azure AD B2C para gerenciar acesso.
- Acesso condicional Azure: Dependendo da certas condições, o nivel de segurança muda. 
- Confiança Zero: assume sempre o pior cenário. 

## Microsoft Purview
Familia de soluções de governança, risco e conformidade de dados. Pode gerenciar os dados na Azure, local ou em outras nuvens. 

## Bloqueios
Exclusão: O usuário pode ler e modificar o recurso
ReadOnly: O usuário só pode ler o recurso. 

## Azure Resource Manager (ARM)
- O ARM (Azure Resource Manager) é o serviço de implantação e gerenciamento do Azure. Ele fornece uma camada de gerenciamento que lhe permite criar, atualizar e excluir recursos em sua conta do Azure. Sempre que você faz qualquer coisa com seus recursos do Azure, o ARM está envolvido.
- Pode criar um arquivo json para configurar o ambiente 
### Bicep

O Bicep é uma linguagem que usa sintaxe declarativa para implantar recursos do Azure. Um arquivo Bicep define a infraestrutura e a configuração. Em seguida, o ARM implanta esse ambiente com base no arquivo Bicep. Embora semelhante a um modelo do ARM, que é escrito em JSON, os arquivos Bicep tendem a usar um estilo mais simples e conciso.

## Integridade de Serviço Azure
- Status do Azure: Visão do status da Azure global. 
- Integridade de Serviço: Informações das regiões e serviços que estão sendo usados. 
- Resource Health: Informações personalizadas. 


## Gerenciamento de Custo
Permite verificar rapidamente os custos de recursos do Azure, alertar e criar orçamentos. 


Erros: 3, 8, 12,13,14, 15, 22, 26, 29, 33, 34, 39
Federated Identity : A integração do Azure AD usando Federated Identity com AD FS (Active Directory Federation Services) permite que os usuários usem suas credenciais de rede existentes do Active Directory local para acessar aplicativos e recursos do Azure. Nessa abordagem, o Azure AD e o AD FS são integrados, permitindo a autenticação federada, onde o AD FS é usado como o provedor de identidade.

 Peering: emparelhamento de rede virtual permite que você conecte duas ou mais redes virtuais no Azure sem interrupção. As redes virtuais aparecerão como uma só para fins de conectividade. O tráfego entre máquinas virtuais em uma rede virtual emparelhada usa infraestrutura de backbone da Microsoft. Assim como o tráfego entre máquinas virtuais na mesma rede, o tráfego é roteado somente pela rede privada da Microsoft
O Azure Bastion é um serviço totalmente gerenciado que fornece um acesso mais seguro e contínuo de protocolo RDP e de protocolo SSH para VMs (máquinas virtuais) sem qualquer exposição por meio de endereços IP públicos.