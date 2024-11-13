# GitHub Repository Search

Este projeto permite que os usuários busquem repositórios públicos do GitHub usando o nome de usuário do GitHub. Ao fornecer um nome de usuário, a aplicação faz uma requisição à API do GitHub para listar todos os repositórios públicos associados a esse usuário.

## Funcionalidades

- **Busca de Repositórios**: Insira o nome de usuário do GitHub para buscar seus repositórios públicos.
- **Exibição de Repositórios**: A lista de repositórios é exibida com nome e descrição, e cada repositório é linkado diretamente para sua página no GitHub.
- **Validação de Entrada**: Caso o campo de nome de usuário esteja vazio, será exibida uma mensagem de erro.
- **Carregamento e Erros**: O status de carregamento é exibido enquanto os dados estão sendo recuperados, e mensagens de erro são apresentadas se houver algum problema.

## Tecnologias Utilizadas

- **Vue.js**: Framework JavaScript utilizado para construir a interface do usuário.
- **API GitHub**: Utilizada para buscar os repositórios públicos do usuário do GitHub.
- **Tailwind CSS**: Utilizado para estilizar a aplicação de forma rápida e responsiva.

## Como Rodar o Projeto

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/svitorz/github_repository_search
   ```

2. **Instale as dependências**:
   No diretório do projeto, execute:
   ```bash
   npm install
   ```

3. **Inicie o servidor de desenvolvimento**:
   Após a instalação, inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```

4. **Acesse a aplicação**:
   Abra seu navegador e acesse [http://localhost:5173](http://localhost:3000) para visualizar a aplicação em funcionamento.

## Como Usar

1. Insira o nome de usuário do GitHub no campo de texto.
2. Clique no botão "Search for repo's" para buscar os repositórios públicos.
3. O carregamento será exibido até que os dados sejam carregados.
4. Caso o nome de usuário esteja vazio, uma mensagem de erro será exibida.
5. Os repositórios encontrados serão listados com o nome e a descrição. Clique no nome do repositório para ser redirecionado para sua página no GitHub.

## Projeto Original

Este projeto foi inspirado na [GitHub Timeline App](https://github.com/florinpop17/app-ideas/blob/master/Projects/3-Advanced/GitHub-Timeline-App.md) do repositório **app-ideas** de **florinpop17**. A aplicação apresentada lá possui um conceito similar de interação com a API do GitHub, e serve como uma excelente base para aprender mais sobre a integração com APIs e o desenvolvimento de interfaces ricas.

## Contribuições

1. Faça um fork do repositório.
2. Crie uma nova branch (`git checkout -b feature/nova-feature`).
3. Faça as alterações e commit com uma mensagem clara (`git commit -m 'Adiciona nova feature'`).
4. Envie a branch (`git push origin feature/nova-feature`).
5. Abra um Pull Request.

## Licença

Este projeto está sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.


