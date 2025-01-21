# SpringTaskManager

## Descrição
Este é um sistema de **gestão de tarefas** desenvolvido utilizando o **Spring Framework** e **Thymeleaf**. Ele permite aos usuários cadastrar, listar, marcar como concluídas, excluir tarefas e aplicar filtros temporários com sessões HTTP. O sistema utiliza o padrão **MVC** para organização do código e armazena os dados em um banco de dados relacional.

## Funcionalidades
1. **Cadastro de Tarefas**:
   - Campos:
     - **Título**: Obrigatório.
     - **Descrição**: Opcional.
     - **Prazo de Conclusão**: Data limite para concluir a tarefa.
2. **Listagem de Tarefas**:
   - Exibe todas as tarefas cadastradas em uma tabela com as colunas:
     - Título.
     - Descrição.
     - Status (Concluída ou Não Concluída).
     - Prazo de Conclusão.
3. **Marcar Conclusão**:
   - Possibilidade de marcar ou desmarcar uma tarefa como concluída.
4. **Exclusão de Tarefas**:
   - Permite excluir tarefas individualmente.
5. **Filtros Temporários**:
   - Implementados com **sessões HTTP** para:
     - Filtrar por status (Concluída ou Não Concluída).
     - Filtrar por prazo.
     - Filtrar por palavra-chave.
   - Os filtros são removidos automaticamente ao expirar a sessão.
6. **Persistência**:
   - As tarefas são armazenadas em um banco de dados relacional.

## Tecnologias Utilizadas
- **Spring Framework**
- **Thymeleaf**
- **Spring MVC**
- **MySQL**

## Configuração do Banco de Dados
Para configurar o banco de dados, utilize o seguinte comando SQL para criar a tabela necessária:

```sql
CREATE TABLE `tarefa` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `titulo` VARCHAR(200) NOT NULL,
  `descricao` VARCHAR(500),
  `concluida` BOOLEAN DEFAULT FALSE,
  `prazo` DATE NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
