# MovieDash

Uma aplicação web moderna para explorar e gerenciar filmes utilizando a API do The Movie Database (TMDB). Este projeto foi desenvolvido como prática das tecnologias React, TypeScript e Tailwind CSS, focando em boas práticas de arquitetura e organização de código.

## Tecnologias Utilizadas

- **React 19** - Biblioteca para construção de interfaces
- **TypeScript** - Superset JavaScript com tipagem estática
- **Tailwind CSS** - Framework CSS utility-first
- **Redux Toolkit** - Gerenciamento de estado global
- **React Router** - Navegação e roteamento
- **Axios** - Cliente HTTP para consumo da API
- **Vite** - Build tool e dev server
- **TMDB API** - API pública para dados de filmes

## Funcionalidades

- Navegação por filmes populares, mais bem avaliados e próximos lançamentos
- Busca de filmes com debounce para otimização de requisições
- Visualização detalhada de filmes incluindo elenco, trailers e recomendações
- Sistema de favoritos com persistência local
- Interface responsiva e moderna
- Carregamento otimizado com estados de loading e erro

## Arquitetura

O projeto utiliza uma arquitetura modular baseada em features, onde cada módulo possui sua própria estrutura independente:

```
src/
├── modules/
│   ├── home/              # Página inicial e listagens
│   ├── search/            # Funcionalidade de busca
│   ├── movie-details/     # Detalhes do filme
│   └── favorites/         # Gerenciamento de favoritos
├── shared/                # Recursos compartilhados
│   ├── services/          # Configuração da API
│   └── types/             # Tipos TypeScript globais
└── store/                 # Configuração do Redux
```

Cada módulo segue a estrutura:
- **components/** - Componentes React específicos
- **pages/** - Páginas do módulo
- **services/** - Chamadas à API
- **store/** - Slices do Redux
- **router/** - Rotas do módulo
- **types/** - Tipos TypeScript

### Principais Destaques Técnicos

**State Management**: Utiliza Redux Toolkit com slices modulares para cada feature, facilitando manutenção e escalabilidade.

**Requisições Otimizadas**: Implementação de `Promise.all` para requisições paralelas e debounce na busca para evitar chamadas desnecessárias à API.

**Persistência**: Middleware customizado para persistir favoritos no localStorage com sincronização automática.

**Tipagem Forte**: Interfaces TypeScript detalhadas para respostas da API e estados da aplicação, garantindo type-safety.

**Componentização**: Separação clara entre componentes de apresentação e containers com lógica de negócio.

## Configuração do Projeto

### Pré-requisitos

- Node.js 16+
- Chave de API do TMDB

### Instalação

1. Clone o repositório
2. Instale as dependências:
   ```bash
   npm install
   ```

3. Crie um arquivo `.env` na raiz do projeto:
   ```
   VITE_TMDB_API_KEY=sua_chave_api_aqui
   ```

4. Execute o projeto:
   ```bash
   npm run dev
   ```

## Scripts Disponíveis

- `npm run dev` - Inicia o servidor de desenvolvimento
- `npm run build` - Gera build de produção
- `npm run preview` - Visualiza build de produção
- `npm run lint` - Executa linter ESLint

## Obtendo Chave da API

- Pode ser obtida em [The Movie Database](https://www.themoviedb.org/)
