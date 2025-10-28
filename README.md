# pahenn Custom Drizzle Fork

> **Note**: This is a custom-patched version of drizzle-orm with MSSQL improvements.
>
> **Fork**: https://github.com/pahenn/drizzle-orm
> **Branch**: `alternation-engine-mssql-patches`
> **Upstream**: git@github.com:drizzle-team/drizzle-orm.git (branch: `alternation-engine`)
>
> **Patches Applied**:
> - MSSQL duplicate index/column/constraint names converted to warnings instead of fatal errors
> - Modified files: `drizzle-kit/src/cli/commands/{generate,pull}-mssql.ts`, `drizzle-kit/src/dialects/mssql/serializer.ts`
> - Fixes compatibility with legacy MSSQL databases that reuse index names across tables

## Using This Fork in Another Project

### Option 1: Git Subtree (Recommended for monorepos)

```bash
cd /path/to/new-project
git remote add drizzle-fork git@github.com:pahenn/drizzle-orm.git
git subtree add --prefix=packages/drizzle-orm drizzle-fork alternation-engine-mssql-patches --squash
```

Then reference as workspace dependency:

```json
{
  "dependencies": {
    "drizzle-orm": "workspace:*",
    "drizzle-kit": "workspace:*"
  }
}
```

### Option 2: Local Clone (For standalone projects)

```bash
git clone git@github.com:pahenn/drizzle-orm.git ~/drizzle-orm-fork
cd ~/drizzle-orm-fork
git checkout alternation-engine-mssql-patches
pnpm install && pnpm build
```

Then reference as file dependency:

```json
{
  "dependencies": {
    "drizzle-orm": "file:~/drizzle-orm-fork/drizzle-orm",
    "drizzle-kit": "file:~/drizzle-orm-fork/drizzle-kit"
  }
}
```

---

<div align="center">
  <img src="./misc/readme/logo-github-sq-dark.svg#gh-dark-mode-only" />
  <img src="./misc/readme/logo-github-sq-light.svg#gh-light-mode-only" />
</div>

<br/>
<div align="center">
  <h3>Headless ORM for NodeJS, TypeScript and JavaScript 🚀</h3>
  <a href="https://orm.drizzle.team">Website</a> •
  <a href="https://orm.drizzle.team/docs/overview">Documentation</a> •
  <a href="https://x.com/drizzleorm">Twitter</a> •
  <a href="https://driz.link/discord">Discord</a>
</div>

<br/>
<br/>

### What's Drizzle?

Drizzle is a modern TypeScript ORM developers [wanna use in their next project](https://stateofdb.com/tools/drizzle).
It is [lightweight](https://bundlephobia.com/package/drizzle-orm) at only ~7.4kb minified+gzipped, and it's tree shakeable with exactly 0 dependencies.

**Drizzle supports every PostgreSQL, MySQL and SQLite database**, including serverless ones like [Turso](https://orm.drizzle.team/docs/get-started-sqlite#turso), [Neon](https://orm.drizzle.team/docs/get-started-postgresql#neon), [Xata](xata.io), [PlanetScale](https://orm.drizzle.team/docs/get-started-mysql#planetscale), [Cloudflare D1](https://orm.drizzle.team/docs/get-started-sqlite#cloudflare-d1), [FlyIO LiteFS](https://fly.io/docs/litefs/), [Vercel Postgres](https://orm.drizzle.team/docs/get-started-postgresql#vercel-postgres), [Supabase](https://orm.drizzle.team/docs/get-started-postgresql#supabase) and [AWS Data API](https://orm.drizzle.team/docs/get-started-postgresql#aws-data-api). No bells and whistles, no Rust binaries, no serverless adapters, everything just works out of the box.

**Drizzle is serverless-ready by design**. It works in every major JavaScript runtime like NodeJS, Bun, Deno, Cloudflare Workers, Supabase functions, any Edge runtime, and even in browsers.  
With Drizzle you can be [**fast out of the box**](https://orm.drizzle.team/benchmarks) and save time and costs while never introducing any data proxies into your infrastructure.

While you can use Drizzle as a JavaScript library, it shines with TypeScript. It lets you [**declare SQL schemas**](https://orm.drizzle.team/docs/sql-schema-declaration) and build both [**relational**](https://orm.drizzle.team/docs/rqb) and [**SQL-like queries**](https://orm.drizzle.team/docs/select), while keeping the balance between type-safety and extensibility for toolmakers to build on top.

### Ecosystem

While Drizzle ORM remains a thin typed layer on top of SQL, we made a set of tools for people to have best possible developer experience.

Drizzle comes with a powerful [**Drizzle Kit**](https://orm.drizzle.team/kit-docs/overview) CLI companion for you to have hassle-free migrations. It can generate SQL migration files for you or apply schema changes directly to the database.

We also have [**Drizzle Studio**](https://orm.drizzle.team/drizzle-studio/overview) for you to effortlessly browse and manipulate data in your database of choice.

### Documentation

Check out the full documentation on [the website](https://orm.drizzle.team/docs/overview).

### Our sponsors ❤️

<p align="center">
<a href="https://drizzle.team" target="_blank">
<img src='https://api.drizzle.team/v2/sponsors/svg'/>
</a>
</p>
