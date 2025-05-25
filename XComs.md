
# Compartilhamento de Dados entre DAGs

O XCom é um recurso nativo do Airflow para compartilhar dados de tarefas. Esse recurso permite que as tarefas troquem metadados de tarefas ou pequenas quantidades de dados. Eles são definidos por chave, valor e data.

Os XComs podem ser enviados (xcom.push) ou recebidos (xcom.pull) por uma tarefa. Quando enviado por uma tarefa, ele é armazenado no banco de dados do Airflow e fica disponível para todas as outras tarefas.

Esse recurso deve ser utilizado apenas para passar pequenas quantidades de dados entre as tarefas. Ele não foi projetado para passar dados como DataFrames ou semelhantes. Para casos como esse, podemos utilizar o armazenamento de dados intermediário, que é mais apropriado para grandes blocos de dados.

More Infos:

https://airflow.apache.org/docs/apache-airflow/2.3.2/concepts/xcoms.html#custom-xcom-backends
https://airflow.apache.org/docs/apache-airflow/2.3.2/concepts/xcoms.html#xcoms