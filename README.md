Essa API foi organizada em pastas para manter o código limpo, modular e fácil de entender. Abaixo está uma descrição do que cada pasta faz:
1. controllers/

Essa pasta contém os arquivos responsáveis por receber as requisições da rota e repassar para os serviços. Também é aqui que definimos as respostas que a API vai retornar (status, mensagens, dados etc).

    Exemplo: quando você chama GET /tarefas, o controller busca as tarefas e devolve o JSON com os dados.

2. routes/

Aqui ficam definidas as rotas da API. Cada rota representa um endpoint que o usuário pode acessar, como criar, listar, editar ou deletar uma tarefa.

    Exemplo: POST /tarefas é uma rota que vai usar uma função do controller para criar uma nova tarefa.

3. services/

A lógica principal da aplicação fica aqui. Os serviços são responsáveis por manipular os dados (adicionar, editar, deletar, etc.). Eles não sabem nada sobre HTTP, só sobre os dados.

    Exemplo: o service recebe uma tarefa, valida e adiciona ela no banco (ou no caso, no array).

4. middlewares/

Aqui colocamos funções que rodam antes das requisições chegarem no controller. Elas servem, por exemplo, para validar se os dados estão corretos.

    Exemplo: impedir que uma tarefa com título muito curto seja salva.

5. utils/

São funções auxiliares, como logs ou tratadores de erros. Essas funções ajudam a manter o restante do código mais limpo.

    Exemplo: imprimir no terminal sempre que uma tarefa for criada ou deletada.

6. database/

Simula um banco de dados com um array em memória. Todas as tarefas são armazenadas temporariamente nesse array.

    Obs: como não é um banco real, os dados se perdem quando o servidor reinicia.

7. app.js

Esse é o arquivo principal da aplicação. Ele inicia o servidor Express, aplica os middlewares e ativa as rotas.

    É por aqui que o sistema começa a rodar.

8. package.json

Arquivo padrão do Node.js. Guarda informações sobre o projeto (nome, versão, scripts) e as dependências instaladas.
