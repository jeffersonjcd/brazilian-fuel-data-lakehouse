# Dicionário de Dados

## 1. Fonte

- **Instituição:** Agência Nacional do Petróleo, Gás Natural e Biocombustíveis (ANP).
- **Conjunto:** Série Histórica de Preços de Combustíveis.
- **Arquivo de trabalho:** `combustivel.csv`.
- **Período selecionado:** primeiro semestre de 2026.
- **Categoria:** combustíveis automotivos.
- **Formato:** CSV.
- **Tamanho observado:** aproximadamente 69 MB.
- **Codificação observada:** UTF-8.
- **Delimitador observado:** ponto e vírgula (`;`).

Fonte oficial:

https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/serie-historica-de-precos-de-combustiveis

## 2. Características observadas

- Os campos de preço utilizam vírgula como separador decimal.
- Existem campos vazios.
- O arquivo contém identificadores de revendas e informações geográficas.
- O arquivo original deverá ser preservado sem modificações na camada Bronze.

## 3. Regras preliminares de tipagem

| Campo lógico | Tipo de destino | Regra |
|---|---|---|
| CNPJ da revenda | STRING | Preservar como identificador textual |
| Data da coleta | DATE | Validar o formato antes da conversão |
| Valor de venda | DECIMAL | Interpretar corretamente a vírgula decimal |
| Valor de compra | DECIMAL, anulável | Preservar valores ausentes como nulos |
| Região | STRING | Preservar o valor de origem |
| Estado | STRING | Preservar a sigla da UF |
| Município | STRING | Preservar acentos e caracteres especiais |
| Revenda | STRING | Preservar o nome original |
| Produto | STRING | Preservar o nome original |
| Unidade de medida | STRING | Preservar a unidade informada |
| Bandeira | STRING | Preservar o valor de origem |

Os nomes físicos das colunas, os formatos exatos e os tipos
definitivos serão confirmados pela inspeção do cabeçalho e
dos registros reais do arquivo.

## 4. Regras de qualidade a implementar

- Validar a quantidade e a ordem das colunas.
- Identificar registros malformados.
- Verificar a conversão de datas e valores monetários.
- Preservar identificadores como texto.
- Distinguir campos vazios de erros de parsing.
- Registrar a quantidade de registros lidos e rejeitados.
- Evitar arredondamentos não justificados nos valores monetários.

## 5. Limites deste documento

Este documento registra as características observadas até o momento
e as regras preliminares de tratamento.

As regras serão atualizadas após a validação automatizada do esquema
e da qualidade dos dados.