# 📘 Fundamentos Essenciais da Engenharia de Dados (2026)

> Um guia de referência rápida com os principais conceitos da Engenharia de Dados moderna.

---

# 📚 Índice

1. Engenharia de Dados
2. ETL (Extract, Transform, Load)
3. ELT (Extract, Load, Transform)
4. Processamento Batch (Lote)
5. Processamento Streaming (Fluxo)
6. Pipeline de Dados
7. Orquestração

---

# 1. Engenharia de Dados

## 📖 O que é?

É a área responsável por projetar, construir e manter sistemas que transformam dados brutos em informações confiáveis, organizadas e prontas para consumo.

## 🎯 Objetivo

Criar mecanismos para coletar, armazenar, transformar e disponibilizar dados para análise, Business Intelligence e Inteligência Artificial.

## ⚙️ Como funciona

O engenheiro de dados gerencia todo o ciclo de vida dos dados:

```text
Fontes → Ingestão → Armazenamento → Transformação → Consumo
```

## 🧩 Principais componentes

- Sistemas de origem
- Camada de ingestão
- Armazenamento escalável
- Motores de processamento
- Ferramentas de entrega

## ✅ Vantagens

- Fonte única da verdade (Single Source of Truth)
- Escalabilidade
- Automação de processos
- Dados consistentes

## ❌ Desvantagens

- Alta complexidade técnica
- Manutenção constante
- Dependência da qualidade dos dados de origem

## 💼 Casos de uso

- Data Warehouse
- Data Lake
- Business Intelligence
- Machine Learning
- Integração entre sistemas

## 💡 Exemplos práticos

- Consolidar vendas de um aplicativo para relatórios financeiros.
- Criar pipelines para detectar fraudes bancárias em tempo real.

## 🔗 Relação com outros conceitos

É a base para Ciência de Dados, Analytics e Machine Learning.

## 🛠️ Ferramentas

- Python
- SQL
- Spark
- Airflow
- dbt
- AWS
- Azure
- Google Cloud

## 📌 Boas práticas

- Simplicidade
- Modularização
- Segurança desde o design
- Controle de custos (FinOps)

## 🚀 Tendências

- Live Data Stack
- Streaming First
- IA para criação automática de pipelines

## 📝 Resumo

- Base para IA e BI.
- Gerencia todo o ciclo dos dados.
- Exige conhecimento em software e bancos de dados.
- Atua como arquiteto de fluxos de dados.
- Responsável por segurança e governança.

---

# 2. ETL (Extract, Transform, Load)

## 📖 O que é?

Processo tradicional onde os dados são:

1. Extraídos
2. Transformados
3. Carregados

## 🎯 Objetivo

Preparar os dados antes que cheguem ao banco de destino.

## ⚙️ Fluxo

```text
Origem
   │
Extract
   │
Transform
   │
Load
   │
Destino
```

## 🧩 Componentes

- Ferramentas ETL
- Área de staging
- Motores de transformação

## ✅ Vantagens

- Banco final recebe apenas dados limpos.
- Evita sobrecarga no destino.

## ❌ Desvantagens

- Mais lento.
- Necessita infraestrutura intermediária.

## 💼 Casos de uso

- Migração de sistemas legados
- Data Warehouses tradicionais

## 💡 Exemplos

- Tratar CSVs em Python antes do BigQuery.
- Migrar ERP para Data Warehouse.

## 🔗 Relação

É o modelo clássico que deu origem ao ELT.

## 🛠️ Ferramentas

- Pentaho
- Talend
- Informatica
- AWS Glue

## 📌 Boas práticas

- Transformações simples
- Documentação completa

## 🚀 Tendências

Evolução para processamento em streaming (STL).

## 📝 Resumo

- Transforma antes de carregar.
- Ideal para bancos menos robustos.
- Alto controle de qualidade.
- Pode limitar Big Data.
- Usa infraestrutura intermediária.

---

# 3. ELT (Extract, Load, Transform)

## 📖 O que é?

Paradigma moderno em que os dados são carregados primeiro e transformados posteriormente.

## 🎯 Objetivo

Aproveitar o processamento massivo da nuvem.

## ⚙️ Fluxo

```text
Origem
   │
Extract
   │
Load
   │
Transform
   │
Consumo
```

## 🧩 Componentes

- Data Lake
- Lakehouse
- Motores SQL
- Camadas Bronze/Silver/Gold

## ✅ Vantagens

- Preserva os dados brutos.
- Muito flexível.
- Reprocessamentos são simples.

## ❌ Desvantagens

- Pode gerar Data Swamp.
- Requer boa governança.

## 💼 Casos de uso

- Modern Data Stack
- Arquitetura Medallion

## 💡 Exemplos

- Armazenar JSON bruto no S3.
- Transformar dados usando dbt no Snowflake.

## 🔗 Relação

Base da arquitetura Medallion.

## 🛠️ Ferramentas

- dbt
- Snowflake
- BigQuery
- Databricks
- Airbyte

## 📌 Boas práticas

Utilizar camadas Bronze → Silver → Gold.

## 🚀 Tendências

Lakehouse como padrão de mercado.

## 📝 Resumo

- Carrega antes de transformar.
- Armazena dados brutos.
- Grande flexibilidade.
- Escala facilmente.
- Base do Analytics Engineering.

---

## 📊 ETL × ELT

| Característica | ETL                        | ELT                        |
| -------------- | -------------------------- | -------------------------- |
| Ordem          | Extract → Transform → Load | Extract → Load → Transform |
| Transformação  | Antes do destino           | No destino                 |
| Armazenamento  | Apenas dados limpos        | Dados brutos e refinados   |
| Flexibilidade  | Menor                      | Maior                      |

---

# 4. Processamento Batch (Lote)

## 📖 O que é?

Processamento periódico de grandes volumes de dados.

## 🎯 Objetivo

Maximizar eficiência quando baixa latência não é necessária.

## ⚙️ Funcionamento

```text
Dados acumulados
        │
     Processamento
        │
 Resultado
```

## 🧩 Componentes

- Agendadores
- Spark
- Arquivos Parquet

## ✅ Vantagens

- Simples
- Econômico
- Fácil de reprocessar

## ❌ Desvantagens

- Dados ficam disponíveis apenas após o processamento.

## 💼 Casos de uso

- Relatórios
- Folha de pagamento
- Backups
- Treinamento de IA

## 💡 Exemplos

- Processar vendas diariamente.
- Calcular folha mensal.

## 🛠️ Ferramentas

- Apache Spark
- AWS Glue
- SQL

## 📌 Boas práticas

- Idempotência
- Monitoramento

## 🚀 Tendências

Micro-batches.

## 📝 Resumo

- Dados finitos.
- Alto throughput.
- Execução agendada.
- Muito utilizado.
- Fácil manutenção.

---

# 5. Processamento Streaming

## 📖 O que é?

Processamento contínuo dos dados à medida que eles chegam.

## 🎯 Objetivo

Baixa latência.

## ⚙️ Fluxo

```text
Evento
   │
Broker
   │
Processamento
   │
Ação
```

## 🧩 Componentes

- Producers
- Kafka
- Flink
- Spark Streaming

## ✅ Vantagens

- Resposta em tempo real.
- Eventos imediatos.

## ❌ Desvantagens

- Maior custo.
- Alta complexidade.

## 💼 Casos de uso

- IoT
- Fraudes
- Dashboards em tempo real

## 💡 Exemplos

- Corridas de aplicativos.
- Monitoramento durante Black Friday.

## 🛠️ Ferramentas

- Kafka
- Kinesis
- Flink
- Spark Streaming

## 📌 Boas práticas

- Watermarks
- Lógica simples

## 🚀 Tendências

Real Time Data Engineering.

## 📝 Resumo

- Dados infinitos.
- Baixa latência.
- Alta disponibilidade.
- Processamento contínuo.
- Base da automação inteligente.

---

## 📊 Batch × Streaming

| Característica | Batch      | Streaming             |
| -------------- | ---------- | --------------------- |
| Dados          | Finito     | Infinito              |
| Latência       | Horas/Dias | Segundos/Milisegundos |
| Complexidade   | Menor      | Maior                 |
| Custo          | Menor      | Maior                 |

---

# 6. Pipeline de Dados

## 📖 O que é?

Fluxo automatizado responsável por mover dados entre sistemas.

## 🎯 Objetivo

Transformar dados brutos em produtos de dados.

## ⚙️ Fluxo

```text
Origem
   │
Ingestão
   │
Armazenamento
   │
Transformação
   │
Entrega
```

## 🧩 Componentes

- APIs
- CDC
- Spark
- dbt
- Camadas Medallion

## ✅ Vantagens

- Automação
- Linhagem
- Escalabilidade

## ❌ Desvantagens

- Dívida técnica quando mal projetado.

## 💼 Casos de uso

- Dashboards
- IA
- Integração de sistemas

## 💡 Exemplos

- Pipeline de logs.
- CRM → Marketing.

## 🛠️ Ferramentas

- Airbyte
- Fivetran
- Spark
- Snowflake
- dbt

## 📌 Boas práticas

- Testes automatizados
- Versionamento
- Monitoramento

## 🚀 Tendências

Pipelines autônomos utilizando IA.

## 📝 Resumo

- Espinha dorsal da Engenharia de Dados.
- Modular.
- Automatizado.
- Observável.
- Gera valor para o negócio.

---

# 7. Orquestração

## 📖 O que é?

Coordenação das tarefas que compõem um pipeline.

## 🎯 Objetivo

Garantir a ordem correta das execuções.

## ⚙️ Fluxo

```text
Task A
   │
   ▼
Task B
   │
   ▼
Task C
```

## 🧩 Componentes

- DAGs
- Schedulers
- Operadores
- Sensores

## ✅ Vantagens

- Automação
- Monitoramento
- Recuperação de falhas

## ❌ Desvantagens

- Infraestrutura adicional

## 💼 Casos de uso

- ETLs complexos
- Processamentos agendados

## 💡 Exemplos

- Esperar API do Facebook e Google Ads antes de unir dados.
- Reiniciar jobs automaticamente após falhas.

## 🛠️ Ferramentas

- Apache Airflow
- Dagster
- Prefect
- AWS Step Functions

## 📌 Boas práticas

- Tarefas pequenas.
- Nunca processar grandes volumes dentro do orquestrador.

## 🚀 Tendências

- Asset-Based Orchestration
- Integração nativa com dbt

## 📝 Resumo

- Controla DAGs.
- Gerencia dependências.
- Centraliza logs.
- Permite backfill.
- Fundamental para escalar plataformas de dados.

---

# 🎯 Mapa Mental

```text
                     Engenharia de Dados
                              │
      ┌───────────────────────┼────────────────────────┐
      │                       │                        │
     ETL                     ELT                 Pipeline
      │                       │                        │
      └──────────────┬────────┘                        │
                     │                                 │
             Batch ou Streaming                        │
                     │                                 │
                     └──────────────► Orquestração ◄───┘
```