# tipos-de-servi-o-de-nuvem
Azure SQL Managed Instance é um serviço PaaS totalmente gerenciado que oferece compatibilidade próxima de 100% com o SQL Server local, automatizando tarefas como patching, backup e alta disponibilidade
Visão Geral: Azure SQL Managed Instance
Azure SQL Managed Instance é um serviço PaaS totalmente gerenciado que oferece compatibilidade próxima de 100% com o SQL Server local, automatizando tarefas como patching, backup e alta disponibilidade 
MSSQL Tips

 Pré-requisitos
Ter uma assinatura Azure e acesso de SQL Managed Instance Contributor ou permissão equivalente .

Ter instalado o módulo PowerShell Az.SQL atualizado ou Azure CLI .

 Criando a Instância via Portal
Acesse o Azure Portal, selecione “Azure SQL” e clique em +Create, escolhendo “Managed Instance” 
Microsoft Learn

Na aba Basics, informe:

| Campo             | Sugestão                                                                      |
| ----------------- | ----------------------------------------------------------------------------- |
| Subscription      | Sua assinatura ativa                                                          |
| Resource Group    | Novo ou existente                                                             |
| Nome da Instância | Conforme regras de nomenclatura                                               |
| Região            | Onde será provisionada                                                        |
| Tier de Serviço   | Geral: *General Purpose* (padrão)                                             |
| Hardware          | Série Gen5, ajustando **vCores** (ex: 8) e **Storage** ([Microsoft Learn][1]) |
| Autenticação      | SQL Auth ou Azure AD (mais seguro)                                            |
| Backup Redundancy | Recomendado: georredundante                                                   |

[1]: https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql&utm_source=chatgpt.com "Quickstart: Create Azure SQL Managed Instance - Learn Microsoft"

Na aba Networking, configure:

Rede Virtual/Sub-rede (nova ou existente compatível).

Public endpoint: geralmente Disabled, mantendo a instância acessível apenas via rede interna 
MSSQL 
Microsoft Learn
MSSQL Tips



Se necessário, libere acessos específicos (ex: via VNet, serviços Azure, internet para testes).

Nas abas Security, Additional Settings, e Tags, revise ou personalize collation, fuso horário, janela de manutenção e metadados como “Owner” ou “Environment” 
Microsoft Learn.

Revise tudo em Review + create e clique em Create. O provisionamento leva alguns minutos até algumas horas 
Microsoft Learn.

 Após a Criação
Acompanhe o status via Notifications no portal ou CLI/Powershell .

Após concluído, obtenha o FQDN da instância para conexão (ex: minha-instancia.xxx.database.windows.net) 
Microsoft Learn.

Crie bancos de dados diretamente sobre a Managed Instance, definindo nomes, collation e opções de restauração 
MSSQL Tips.


✅ Conclusão
O Azure SQL Managed Instance oferece um ambiente PaaS ideal para migrar cargas de SQL Server com o mínimo esforço. A experiência via portal é guiada e segura, mas requer atenção em cada etapa — desde rede até autenticação e backups — para garantir performance, segurança e conformidade.
