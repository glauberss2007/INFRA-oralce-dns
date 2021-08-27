# oci-dns
![image](https://user-images.githubusercontent.com/22028539/131153906-6345d3ec-78f1-4d42-8b23-dd684d34a22c.png)

The Domain Name System (DNS) is a distributed internet system that maps human-readable names (like www.Oracle.com) to IP addresses and serves as the first link in the customers’ digital supply chain. Oracle's globally distributed DNS service offers enhanced DNS performance, resiliency, and scalability, so that end users connect to customers’ application as quickly as possible, from wherever they are.

## DNS Service Components
1. Domain: example.com or oracle.com
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

[oci_dns_zone](https://github.com/glauberss2007/oci-dns/blob/main/oci_dns_zone.yaml)
[Explanation](https://registry.terraform.io/providers/hashicorp/oci/latest/docs/resources/dns_zone)

References: https://registry.terraform.io/providers/hashicorp/oci/latest/docs/resources/dns_zone

## Serviço DNS
### Usando a Visão Geral do Gerenciamento do DNS para Gerenciar Serviços do DNS
### Conceitos Básicos do DNS
### Gerenciando Zonas de Serviço do DNS
### Configurando Zonas de DNS Reversas
### Registros de Recursos Suportados
### Formatando um Arquivo de Zona
### Gerenciando Redirecionamentos de HTTP
### Gerenciando Chaves TSIG
### Testando o DNS Usando a Ferramenta dig da BIND
### DNS Privado
#### Solução de problemas
### Métricas do DNS

