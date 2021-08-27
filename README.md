# oci-dns
![image](https://user-images.githubusercontent.com/22028539/131153906-6345d3ec-78f1-4d42-8b23-dd684d34a22c.png)

The Domain Name System (DNS) is a distributed internet system that maps human-readable names (like www.Oracle.com) to IP addresses and serves as the first link in the customers’ digital supply chain. Oracle's globally distributed DNS service offers enhanced DNS performance, resiliency, and scalability, so that end users connect to customers’ application as quickly as possible, from wherever they are.

## DNS Service Components
1. domain: example.com or oracle.com
2. zone: parte do namespace de DNS
3. label: labels são pré-anexados ao nome da zona ("www' de um site ou "docs" de docs.us-ashburn-1.oraclecloud.com, por exemplo )
4. child zone: subdomínios independentes com seus próprios registros
5. registro de recurso (RDATA): o registro depende do tipo [Record types description](https://docs.oracle.com/en-us/iaas/Content/DNS/Reference/supporteddnsresource.htm)
6. delegação: servidores de nomes gerenciavel contendo os DNSs

## GUI console access

[Link of GUI console](https://console.sa-saopaulo-1.oraclecloud.com/)

Select Networking > DNS > DNS-Zones > Add Zone

1. Method (Manual Import) 
2. Zone Name
3. Zone Type (Primary | Secondary)
4. Add 
5. Select created Zone
6. Add record
7. Publish Changes to update zone

Domains delegation to OCI:

1. Overview
2. Customer account info
3. Copy the four Nameservers
4. Log to your domain registre portal and append a NS record for each nameserver in your 

## Using terraform
1. [oci_dns_zone](https://github.com/glauberss2007/oci-dns/blob/main/oci_dns_zone.yaml)
2. [oci_dns_record](https://registry.terraform.io/providers/hashicorp/oci/latest/docs/resources/dns_record)
3. [oci_dns_resolver](https://registry.terraform.io/providers/hashicorp/oci/latest/docs/resources/dns_resolver)
4. [oci_dns_view](https://registry.terraform.io/providers/hashicorp/oci/latest/docs/resources/dns_view)

References: https://registry.terraform.io/providers/hashicorp/oci/latest/docs/data-sources/dns_records

## Serviço DNS

Limits: 
1. 1000 zones by account
2. 25000 registers by zone

## IAM Policies needed
1. Para ativar todas as operações em zonas para um grupo de usuários específico: "Allow group <GroupName> to manage dns in tenancy <TenancyName>"
2. Para ativar um grupo específico para ler zonas: "Allow group <GroupName> to read zones in tenancy <TenancyName>"
3. Para criar um grupo de gerenciamento DNS somente para leitura: "Allow group <GroupName> to read dns in tenancy <TenancyName>"

### Usando a Visão Geral do Gerenciamento do DNS para Gerenciar Serviços do DNS
  1. Zonas: contêm os registros do DNS
  2. Traffic Management Steering Policies: orientar o tráfego baseado em integridade do ponto final e origens geográficas de solicitações de DNS.
  3. Serviço de suporte: links para serviços adicionais

### Conceitos Básicos do DNS 
  
  O DNS (Domain Name System) converte nomes de domínios legíveis por seres humanos em endereços IP legíveis por máquina. Um servidor de nome DNS armazena registros de DNS para uma zona e responde a consultas com relação ao respectivo banco de dados. Quando você digita um nome de domínio em seu browser, seu sistema operacional consulta diversos servidores de nome DNS até encontrar o servidor de nome autorizado para esse domínio. O servidor de nome autorizado responde com um endereço IP ou outros dados de registro solicitados. A resposta é, então, retransmitida para o browser e o registro de DNS é resolvido para a página Web.
  
  - [dig](https://docs.oracle.com/pt-br/iaas/Content/DNS/Tasks/testingdnsusingdig.htm#Testing_DNS_Using_BINDS_dig_Tool)
  
### Gerenciando Zonas de Serviço do DNS
  #### Console
  
    1. [Adicionar uma zona]
    2. [Atualizar uma zona secundária]
    3. [Excluir uma zona]
    4. [Adicionar um registro de zona]
    5. [Atualizar um registro de zona]
    6. [Excluir um registro de zona]
    7. [Delegar uma zona]
    8. [Mover uma zona para outro compartimento]
    9. [Adicionar uma chave TSIG]
    10. [Remover uma chave TSIG de uma zona]

  #### APIs
    
    1. [GetZone]
    2. [ListZones]
    3. [CreateZone]
    4. [UpdateZone]
    5. [DeleteZone]
    6. [PatchZoneRecords (adicionar ou excluir registros)]
    7. [UpdateZoneRecords]
  
### Configurando Zonas de DNS Reversas
### Registros de Recursos Suportados
### Formatando um Arquivo de Zona
### Gerenciando Redirecionamentos de HTTP
### Gerenciando Chaves TSIG
### Testando o DNS Usando a Ferramenta dig da BIND
### DNS Privado
#### Solução de problemas
### Métricas do DNS

