# O que é um DAG?

**DAG** é a sigla para **Directed Acyclic Graph**, ou **Grafo Acíclico Dirigido**. Vamos entender cada parte:

- **Grafo**: Estrutura matemática composta por **nós** e **arestas**, onde as arestas conectam os nós.
- **Dirigido**: O fluxo acontece apenas em uma direção, ou seja, uma tarefa depende da anterior.
- **Acíclico**: Não existem ciclos. A execução sempre avança até um nó final, sem voltar ao início.

## Aplicação no Airflow

No **Apache Airflow**, um DAG representa um **workflow** (fluxo de trabalho) dividido em tarefas menores, chamadas de **tasks**. Cada task executa uma parte da lógica do pipeline de dados.

Assim, um DAG é um **conjunto de tarefas organizadas** de forma que respeitem dependências e ordens de execução, garantindo clareza, modularidade e controle no processo.

## Para se aprofundar

- [Documentação oficial do Airflow sobre DAGs](https://airflow.apache.org/docs/apache-airflow/1.10.12/concepts.html#dags)
- [Artigo da Alura: Airflow - Entendendo os DAGs](https://www.alura.com.br/artigos/airflow-entendendo-dags)
