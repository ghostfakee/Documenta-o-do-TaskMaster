**Frontend:**  React.js para interface de usuário.  
**Backend:** C#  ASP.NET Core para servidor e banco de dados  
**Banco de Dados:**  SQL Server para armazenamento de dados.  
**Integração de IA:**  API fornecida pelo fornecedor dos serviços da IA- OpenGL  


# Modelo de Dados:

| Entidade       | Atributos                                               |
| -------------- | ------------------------------------------------------- |
| Quadro         | id, nome, descrição                                     |
| Lista          | id, nome, quadroId                                      |
| Tarefa         | id, nome, descrição, listaId, prioridade, dataConclusão |
| Sugestão de IA | tarefaId, prioridadeSugerida, dataSugestão              |
