# Aplicação de Cadastro e Listagem de Produtos com Streamlit e SQL Server

Este repositório contém uma aplicação Streamlit para cadastrar e listar produtos, utilizando um banco de dados SQL Server para armazenar as informações. A aplicação permite aos usuários inserir detalhes de produtos (nome, preço, descrição e imagem) e exibi-los em um formato organizado.

## Prints da Aplicação

### FUNCIONAMENTO DA APLICAÇÃO MAIN - UTILIZANDO O COMANDO "STREAMLIT RUN MAIN.PY"  ###

![funcionamento da aplicação main](https://github.com/user-attachments/assets/19020762-cf31-46ea-b237-2014d5536d05)
*Este print mostra o funcionamento da aplicação main.py utilizando streamlit.*

### CADASTRANDO PRODUTO ###

![Cadastrando produto](https://github.com/user-attachments/assets/dbd44f4c-2cd3-4a67-afc1-6df2a356e183)

*Este print mostra o procedimento de cadastramento de produtos.*

### LISTANDO PRODUTO JÁ CADASTRADO - "PRODUTOS BLUSAS" ###

![Listando os produtos já cadastrados blusas](https://github.com/user-attachments/assets/6d9a296b-be49-45f1-8605-a5b22187daef)

*Este print esta listando os produtos blusas já cadastrados.*

### LISTANDO PRODUTO JÁ CADASTRADO - "PRODUTOS CALÇAS" ###

![Listando produtos cadastrados calça](https://github.com/user-attachments/assets/315c8e0e-20f8-40a0-989b-fb1dd9d766ac)

*Este print esta listando os produtos calças já cadastrados.*

### BASE DE DADOS - SQL SERVER LOCAL ###

![Base de dados SQL server](https://github.com/user-attachments/assets/1ac01e86-8f7b-4c81-91b1-9256e7f74a6e)

*Este print mostra a base de dados sqllab1 no SQL SERVER LOCAL, onde estão os produtos já cadastrados, na tabela produtos.*

### Formulário de Cadastro de Produtos ###

![FORMULARIO CADASTRO DE PRODUTO](https://github.com/user-attachments/assets/69369384-c540-4134-b1dc-5aacdd2c39a8)

*Este print mostra o formulário onde os usuários inserem as informações do produto: Nome, Preço, Descrição e Imagem.*

### Lista de Produtos Cadastrados ###

![Lista os produtos cadastrados](https://github.com/user-attachments/assets/6e2a3cc2-7ef5-4465-92c3-539c7618f360)

*Este print exibe a lista de produtos cadastrados, mostrando detalhes como nome, descrição, preço e imagem.*

## Descrição do Processo

O desenvolvimento desta aplicação envolveu as seguintes etapas:

1.  **Configuração do Ambiente:**
    * Instalação das bibliotecas necessárias: `streamlit`, `pymssql`, `python-dotenv`.
    * Configuração das variáveis de ambiente usando `.env` para armazenar informações confidenciais (string de conexão do SQL Server).
    * Criação de um diretório para salvar as imagens localmente.
2.  **Desenvolvimento da Aplicação Streamlit:**
    * Criação de um formulário para entrada de dados do produto (nome, preço, descrição, imagem).
    * Implementação da lógica para salvar os dados do produto no banco de dados SQL Server, incluindo o salvamento da imagem no sistema de arquivos local.
    * Desenvolvimento da funcionalidade para listar os produtos do banco de dados e exibi-los na interface do Streamlit.
    * Utilização do `st.session_state` para manter o estado da aplicação entre as interações do usuário.
    * Implementação de mensagens de sucesso e erro para fornecer feedback ao usuário.
3.  **Interação com o Banco de Dados SQL Server:**
    * Estabelecimento de conexões com o banco de dados SQL Server usando a biblioteca `pymssql`.
    * Execução de operações CRUD (Create, Read) no banco de dados para inserir e recuperar dados de produtos.
    * Utilização de prepared statements para prevenir injeções de SQL.
    * Tratamento de erros de banco de dados para garantir a robustez da aplicação.
4.  **Gerenciamento de Imagens:**
    * Permitir que os usuários carreguem imagens de produtos.
    * Salvar as imagens carregadas em um diretório local no servidor.
    * Armazenar o caminho do arquivo da imagem no banco de dados SQL Server local.
    * Exibir as imagens dos produtos na lista de produtos.

## Insights e Possibilidades Aprendidas

* **Integração Streamlit com Bancos de Dados:** A aplicação demonstra como o Streamlit pode ser efetivamente integrado com bancos de dados relacionais (neste caso, SQL Server) para armazenar e recuperar dados.
* **Gerenciamento de Arquivos com Streamlit:** Aprendi a lidar com o upload de arquivos (imagens) no Streamlit, salvá-los no sistema de arquivos do servidor e armazenar os caminhos no banco de dados.
* **Variáveis de Ambiente e Segurança:** O uso de `.env` para armazenar informações confidenciais é crucial para a segurança da aplicação, evitando a exposição de credenciais em código.
* **Gerenciamento de Estado com `st.session_state`:** O `st.session_state` é essencial para manter o estado da aplicação, permitindo que os dados persistam entre as renderizações.
* **Layout e Estilização:** O código utiliza recursos de layout do Streamlit (`st.columns`) e formatação HTML para exibir os produtos de forma mais organizada e visualmente atraente.
* **Tratamento de Erros:** A implementação de tratamento de erros (try-except blocks) é importante para garantir que a aplicação lide bem com exceções e forneça feedback útil ao usuário.
* **Cache de Dados:** O uso de `st.cache_data` para armazenar em cache os resultados da consulta ao banco de dados melhora o desempenho da aplicação, evitando consultas repetidas desnecessárias.

## Próximos Passos e Possibilidades Futuras

* **Implementar Operações CRUD Completas:** Adicionar funcionalidades para editar (Update) e excluir (Delete) produtos.
* **Validação de Dados:** Implementar validação de dados no formulário para garantir que os dados inseridos pelos usuários sejam válidos (por exemplo, verificar tipos de dados, tamanhos máximos, etc.).
* **Paginação:** Adicionar paginação à lista de produtos para melhorar o desempenho e a usabilidade quando houver muitos produtos.
* **Busca e Filtro:** Implementar funcionalidades de busca e filtro para permitir que os usuários encontrem produtos específicos mais facilmente.
* **Autenticação e Autorização:** Adicionar um sistema de autenticação e autorização para controlar o acesso à aplicação e garantir que apenas usuários autorizados possam cadastrar ou modificar produtos.
* **Melhorias na Interface do Usuário:** Aprimorar a interface do usuário com CSS personalizado ou bibliotecas de componentes Streamlit para torná-la mais atraente e intuitiva.
* **Upload de Imagens para Armazenamento em Nuvem:** Em vez de salvar as imagens localmente, considerar o uso de um serviço de armazenamento em nuvem (como Azure Blob Storage, AWS S3) para armazenar as imagens. (O código no "main.py" já tem parte dessa lógica comentada).
* **Otimização de Desempenho:** Analisar e otimizar o desempenho da aplicação, especialmente em relação às consultas ao banco de dados e ao carregamento de imagens.

## Conclusão

Esta aplicação demonstra o poder do Streamlit para criar rapidamente aplicações web interativas com integração de banco de dados. As possibilidades de expansão são vastas, e este projeto serve como uma base sólida para construir aplicações de gerenciamento de produtos mais complexas e completas.
