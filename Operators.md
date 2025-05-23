# ✈️ Operadores no Apache Airflow

Os **operadores** são **classes do Python** que encapsulam a lógica necessária para executar **uma unidade de trabalho (tarefa)**. Eles definem as **ações a serem realizadas** por uma tarefa, abstraindo grande parte do código que seria necessário escrever manualmente.

Ao instanciar um operador com os parâmetros apropriados, essa instância **se torna uma tarefa executável** dentro de um DAG (Directed Acyclic Graph).

---

## 🔧 Tipos Comuns de Operadores

O Airflow possui uma ampla variedade de operadores prontos para uso. Abaixo estão alguns dos mais utilizados:

| Operador              | Descrição                                                                 |
|-----------------------|---------------------------------------------------------------------------|
| `PythonOperator`      | Executa uma **função Python**.                                            |
| `BashOperator`        | Executa um **comando ou script Bash**.                                    |
| `KubernetesPodOperator` | Executa uma **imagem Docker em um pod do Kubernetes**.                 |
| `SnowflakeOperator`   | Executa uma **consulta no banco de dados Snowflake**.                    |
| `EmailOperator`       | Envia um **e-mail**.                                                      |

> 💡 **Dica:** Se não houver um operador adequado para seu caso de uso, o Airflow permite **criar operadores personalizados**.

---

## 🎯 Características de um Operador

Todo operador no Airflow deve seguir três princípios fundamentais:

1. **Idempotência**  
   > A tarefa deve produzir sempre o **mesmo resultado**, mesmo que seja executada múltiplas vezes com os **mesmos parâmetros**.

2. **Isolamento**  
   > A tarefa deve ser **independente**, sem **compartilhar recursos** com outras tarefas ou operadores.

3. **Atomicidade**  
   > A tarefa deve ser uma **unidade indivisível** de trabalho: ou ela é executada por completo, ou **não é executada**.

---

## 📌 Conclusão

Operadores são **blocos fundamentais** no Airflow, tornando-o uma ferramenta poderosa para orquestração de dados. Com eles, é possível realizar tarefas complexas com **menos código** e maior **clareza na manutenção** dos fluxos de trabalho.

Mais sobre
https://airflow.apache.org/docs/apache-airflow/2.3.2/concepts/operators.html