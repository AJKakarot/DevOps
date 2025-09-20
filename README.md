# Prisma + TypeScript Project

This is a simple Node.js + TypeScript + Prisma setup with PostgreSQL.
It demonstrates creating users and todos using the Prisma Client.

---

## Prerequisites

* Node.js >= 18
* npm
* PostgreSQL database
* Git (optional, for cloning)

---

## Setup

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

2. **Install dependencies**

```bash
npm install
```

3. **Create a `.env` file**
   At the root of your project, add `.env` with your database URL:

```env
DATABASE_URL="postgresql://USER:PASSWORD@HOST:PORT/DATABASE?schema=public"
```

4. **Check Prisma schema**
   The schema is at `prisma/schema.prisma`:

* Models: `User` and `Todo`
* Prisma Client output: `node_modules/.prisma/client` (default)
* Make sure the database matches your `.env` URL

---

## Database setup

1. **Generate Prisma Client**

```bash
npx prisma generate
```

2. **Run migrations**

```bash
npx prisma migrate dev --name init
```

* This will create tables in your PostgreSQL database
* It also regenerates the Prisma client automatically

3. **Optional: Check DB with Prisma Studio**

```bash
npx prisma studio
```

* Opens a browser UI to view and edit database records

---

## Running the project

1. **Compile TypeScript**

```bash
npx tsc
```

2. **Run the compiled JS**

```bash
node dist/index.js
```

---

## Project Structure

```
.
├── src
│   └── index.ts        # main TypeScript file
├── prisma
│   └── schema.prisma   # Prisma schema
├── dist                # compiled JS files
├── node_modules
├── package.json
├── tsconfig.json
└── .env
```

---

## Notes

* **Always run `npx prisma generate`** after changing `schema.prisma`.
* For dev environments, you can safely delete old migrations and run `npx prisma migrate reset`.
* Make sure your `.env` DATABASE\_URL is correct.

---

## License

MIT
