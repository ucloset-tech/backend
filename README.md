# UCloset Backend

Backend do projeto **UCloset** usando **NestJS**, **Prisma** e **PostgreSQL** via Docker.

---

## Pré-requisitos

- Node.js >= 20
- pnpm
- Docker e Docker Compose
- NestJS CLI (opcional, mas útil para gerar módulos, controllers, services)

## 1️⃣ Clonar o repositório

```bash
git clone <URL_DO_REPOSITORIO>
cd backend
```

## 2️⃣ Instalar dependências

```bash
pnpm install
```

## 3️⃣ Configurar variáveis de ambiente

### .env na raiz do projeto

```env
DATABASE_URL="postgresql://ucloset:1234@localhost:5432/ucloset_db?schema=public"
```

## 4️⃣ Subir o banco de dados com Docker

```bash
docker-compose up -d
```

### Verifique se o container está rodando:

```bash
docker ps
```

### Info banco de dados para conectar no dbvear

```
Usuário: ucloset
Senha: 1234
Database: ucloset_db
Porta: 5432
```

## 5️⃣ Rodar migrations e seed do banco

### Rodar migrations

```bash
pnpm run prisma:migrate:dev
```

### Gerar Prisma Client

```bash
pnpm run prisma:generate
```

### Popular o banco (seed)

```bash
pnpm run db:seed
```

## 6️⃣ Rodar o servidor NestJS

```bash
pnpm run start:dev
```

Servidor rodando em http://localhost:3000

Documentação rodando em http://localhost:3000/swagger

## 7️⃣ Dicas de desenvolvimento

Para manter o código consistente e evitar erros:

- **Habilite o "Format on Save" no seu editor** (VSCode)
- **Prettier**: garante formatação automática de código
  - Instale a extensão Prettier no VSCode
  - Configure para rodar ao salvar os arquivos
  - Rodar `pnpm run format` regularmente ajuda a manter o código limpo
- **ESLint**: validação de código e boas práticas
  - Instale a extensão ESLint
  - Garanta que ESLint rode ao salvar o arquivo
  - Rodar `pnpm run lint` regularmente ajuda a manter o código limpo
- **Prisma**: habilite extensões para syntax highlighting e autocomplete
  - Prisma Client para TypeScript
