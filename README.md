# Brazilian Fuel Data Lakehouse

Plataforma de engenharia de dados desenvolvida com tecnologias open source para ingestão, processamento, armazenamento analítico e visualização de dados públicos sobre preços de combustíveis no Brasil.

## Objetivo

Construir um pipeline de dados reproduzível, desde a ingestão da fonte pública até a disponibilização de indicadores analíticos, aplicando conceitos modernos de Data Lakehouse e engenharia de dados.

## Fonte de dados

- **Origem:** Agência Nacional do Petróleo, Gás Natural e Biocombustíveis (ANP).
- **Conjunto:** Série Histórica de Preços de Combustíveis e de GLP.
- **Formato de origem:** CSV.
- **Granularidade:** registros de pesquisas de preços por revenda, produto, data e localidade, conforme os campos disponibilizados pela fonte.
- **Portal oficial:** https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/serie-historica-de-precos-de-combustiveis

Os dados serão obtidos diretamente da fonte oficial. Os arquivos originais não serão versionados neste repositório.

## Arquitetura planejada

| Camada | Responsabilidade |
|---|---|
| Ingestão | Obtenção dos dados, registro de metadados e rastreabilidade |
| Bronze | Preservação dos arquivos originais |
| Silver | Padronização, tipagem e validação dos dados |
| Gold | Modelos analíticos para consultas e visualização |
| Consumo | Consultas SQL e dashboards |

## Tecnologias planejadas

- Python
- Docker Compose
- SeaweedFS
- Apache Spark
- Apache Iceberg
- Apache Polaris
- Trino
- dbt Core
- Apache Airflow
- Apache Superset
- GitHub Actions

As tecnologias serão integradas incrementalmente, com testes de funcionamento e documentação das decisões arquiteturais.

## Princípios do projeto

- Reprodutibilidade do ambiente.
- Preservação e rastreabilidade dos dados de origem.
- Idempotência e possibilidade de reprocessamento.
- Qualidade e consistência dos dados.
- Separação entre armazenamento, catálogo, processamento e consumo.
- Uso de formatos abertos e interoperabilidade.
- Documentação das decisões e dos trade-offs técnicos.

## Status

**Em desenvolvimento — fase de planejamento e preparação da ingestão.**

## Documentação

- [Visão da arquitetura](docs/architecture/overview.md)
- [Decisões arquiteturais](docs/decisions/)
- [Dicionário de dados](docs/data/data-dictionary.md)
- [Procedimentos operacionais](docs/runbook.md)

## Licença

Consulte o arquivo LICENSE para as condições de reutilização do código. A licença do código não substitui os termos aplicáveis aos dados da fonte original.
