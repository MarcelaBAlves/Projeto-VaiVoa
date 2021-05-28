Projeto-VaiVoa

Projeto desenvolvido para processo seletivo empresa VaiVoa

A proposta consiste em criar um artigo blog post sobre um projeto em C# com .NET Core. Deverá ser descrito o passo-a-passo para criação de uma API REST que fornece um sistema de geração de número de cartão de crédito virtual. Esta API deverá gerar números aleatórios para o pedido de novo cartão. Cada cartão gerado deve estar associado a um email para identificar a pessoa que está utilizando. 

Serão utilizados 2 endpoints. Um receberá o email da pessoa e retornará um objeto de resposta com o número do cartão de crédito. O outro, deverá listar em ordem de criação, todos os cartões de crédito virtuais de um solicitante (passando email como parâmetro).

Toda a implementação deverá ser escrita utilizando C# com .NET Core e Entity Framework Core.

Para o desenvolvimento, foi utilizado o Visual Studio 2019.Na primeira etapa veremos como:
- Criar de um projeto de API Web.Adicionar uma classe de modelo e um contecto de banco de dados.
- Fazer scaffold de um controlador com métodos CRUD.Configurar o roteamento, os caminhos de URL e os valores retornados.
- Como chamar a API Web com PostmanAo final desta etapa teremos uma API Web que pode gerenciar itens de tarefas pendentes armazenados em um banco de dados.

Para começar, cria-se um novo projeto no Visual Studio ASP.NET Core Web API. Este modelo de API cria uma classe API com suporte para Swagger, que é usado para gerar páginas úteis de documentação e ajuda para APIs Web. Depois de testado a Swagger é removida.

Foi criada uma classe modelo, que é um conjunto de classes que representam os dados gerenciados pelo aplicativo. Para este Aplicativo será utilizado uma única classe. As classes modelo podem ir em qualquer lugar no projeto, mas a pasta Models é utilizada pela convenção.

O próximo passo é adicionar um contexto de banco de dados. Essa é a classe principal que coordena a funcionalidade do Entity Framework para um modelo de dados. Essa classe é criada derivando-a da classe Microssoft.EntityFrameworkCore.DbContext.

Após criado, é necessário registrar o contexto do banco de dados no contêiner de DI (injeção de dependência), que fornece o serviço aos controladores.

Um Scaffold é usado para gerar a interface do usuário baseada na Web que permite que o usuário exiba e atualize um banco de dados.Em seguida atualizamos o método de criação Post. Esse método:
- Retornará um código de status HTTP 201 se for bem sucedido.
- Adiciona um cabeçalho de Local a resposta.
- Faz uma referência à uma ação para criar o URI de Location do cabeçalho.
 
Para finalizar utilizamos o app Postman para testar o Post, URI, Get.
