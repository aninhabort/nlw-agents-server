# NLW Agents

Projeto desenvolvido durante o evento NLW da Rocketseat.

## Tecnologias e Bibliotecas Principais

- **Node.js** + **TypeScript**
- **Fastify**: Framework web para APIs rápidas e modernas
- **Drizzle ORM** + **drizzle-kit**: ORM e ferramentas para migrations e schema
- **PostgreSQL**: Banco de dados relacional (com suporte a extensões como pgvector)
- **Zod**: Validação de esquemas e variáveis de ambiente
- **Biome**: Linter e formatter para JavaScript/TypeScript

## Estrutura e Padrões

- Organização por responsabilidade: `src/http/routes` para rotas, `src/db/schema` para schemas do banco, `src/db/migrations` para migrations
- Validação de dados e tipos usando Zod e Fastify Type Provider
- Separação de configuração de ambiente (`src/env.ts`)
- Scripts para geração, migração e seed do banco

## Setup do Projeto

1. **Clone o repositório e instale as dependências:**
   ```bash
   npm install
   ```
2. **Configure o banco de dados:**
   - Utilize o Docker Compose para subir o PostgreSQL já com a extensão pgvector:
     ```bash
     docker-compose up -d
     ```
   - O banco será exposto na porta 5432, usuário e senha padrão: `docker`.
3. **Configure o arquivo `.env`** (baseie-se nas variáveis usadas em `src/env.ts`):
   ```env
   PORT=3333
   DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
   ```
4. **Rode as migrations e o seed:**
   ```bash
   npm run db:migrate
   npm run db:seed
   ```
5. **Inicie o servidor em modo desenvolvimento:**
   ```bash
   npm run dev
   ```

## Comandos Úteis

- `npm run dev`: Inicia o servidor com hot reload
- `npm run db:migrate`: Executa as migrations do banco
- `npm run db:seed`: Popula o banco com dados de exemplo

---

Desenvolvido durante o NLW da Rocketseat 🚀
