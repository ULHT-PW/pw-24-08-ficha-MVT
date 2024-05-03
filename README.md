Univesidade Lusófona
**Programação Web**

# Ficha 8: O Poder dos Formulários e Autenticação nas Aplicações Django

Esta ficha tem tarefas para duas semanas de aulas, entre 22 a 3 de maio.

### Objetivo:
* Familiarizar-se com formulários que permitam inserir conteúdos (objectos, 1:N, N:M)
* familiarizar-se com a autenticação.

### Recomendações:
* consultar os slides da aula
* consultar o [repositório](https://github.com/ULHT-PW/bibliotecalusofona/tree/main?tab=readme-ov-file#formul%C3%A1rio-de-cria%C3%A7%C3%A3o-de-novo-autor) com os passos para implementação de operações CRUD através de formulários
* consultar a aplicação [biblio](https://github.com/ULHT-PW/biblio) para integrar autenticação

# 0. autenticação
* crie no seu projeto uma nova aplicação autenticação. 
* criar três grupos de utilizadores: editores de bandas, artigos e curso. Estes podem editar diretamente no admin, visualizando, adicionando e alterando certas tabelas, mas não podendo apagar nada.
* crie pelo menos um utilizador por grupo.
* Integrar na aplicação de autenticação views com funcionalidades de registo, autenticação e recuperação de senha de utilizadores, tal como ensinado na aula. Em particular, para envio de email deverá configurar a conta Google associada como indicado nos slides de modo a habilitar o acesso a APIs (apps menos seguras) [[ref]](https://github.com/ULHT-PW/biblio/blob/main/README.md#aplica%C3%A7%C3%A3o-biblioteca-com-integra%C3%A7%C3%A3o-de-autentica%C3%A7%C3%A3o).
* integrar nas três aplicações no menu um botão que permite fazer login na aplicação.
* restringir o acesso a views de edição de campos a utilizadores autenticados, adaptando o decorador @login_required para só permitir editar utilizadores que façam parte do grupo de utilizadores da aplicação.
   * utilizadores do grupo bandas não deverão poder editar artigos ou adicionar projetos ao curso.
   * o mesmo para artigos e curso.
   * **na app dos artigos, na classe do artigo adicione um campo `autor` que é foreignkey User `autor = models.ForeignKey(User, on_delete=models.CASCADE, related_name='artigos')`. Deve importar a classe User com`  
`from django.contrib.auth.models import User`). pode assim aceder ao nome do utilizador user.first_name e apresentar nos artigos e comentários, etc**
* apenas mostrar botões de editar/criar/apagar se o utilizador estiver autenticado e pertencer ao grupo de utilizadores da aplicação.

# A. aplicação web bandas 🎸
* Se o utilizador estiver autenticado e fizer parte do grupo, torne editáveis todos os dados, permitindo criar, alterar e remover elementos (banda, álbum, música).

# B. aplicação artigos 📚
* Se o utilizador estiver autenticado e fizer parte do grupo, torne editáveis todos os dados (criar, alterar e remover elementos).

# C. aplicação curso 🎓
* Se o utilizador estiver autenticado e fizer parte do grupo, torne editáveis todos os dados (criar, alterar e remover elementos).




