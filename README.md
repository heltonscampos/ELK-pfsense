# ELK-pfsense
Observabilidade do pfSense com ELK Stack

## O que é
As ferramentas da Elastic Stack são muito poderosas com seus três principais componentes, o banco de dados não-relacional Elasticsearch, a ferramenta de ETL, o Logstash, a aplicação Web, o Kibana, que consome os dados do Elasticsearch e por ela é possível montar visualização e dashboards. Existem também os agentes da Stack, os Beats, que coletam informações de servidores e serviços e alimentam ou via Logstash, ou diretamente o Elasticsearch, podendo coletar métricas com o Metricbeat, dados de auditoria com o Auditbeat, dados de Logs com o Filebeat, dentre outros Beats que formam a Stack, deixando a ELK Stack ainda mais completa.

## Objetivo
Nesta pipeline utilizamos apenas as três principais ferramentas forneceidas pela Elastic, o Elasticsearch, Logstash e Kibana. No nosso caso de uso, precisariamos capturar os logs do pfSense+OpenVPN para poder analisar os logs dessas aplicações, montando visualizações e dashboards. 

# Requisitos
1. SO server (No caso usei um Centos8)
2. Logstash, Kibana e Elasticsearch instalados.
3. Conta free no Maxmind para o GeoIP

# Executando
Após criar a conta no Maxmind, conforme exige a documentação: https://www.elastic.co/guide/en/logstash/current/plugins-filters-geoip.html, vamos criar os arquivos de instalação
#mkdir geoip
#cd geoip/
#dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm 
#wget https://github.com/maxmind/geoipupdate/releases/download/v4.0.0/geoipupdate_4.0.0_linux_amd64.rpm 
#rpm -Uvhi geoipupdate_4.0.0_linux_amd64.rpm 

