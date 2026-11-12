# Fixture Notes API

A small Express + Postgres service used as a test fixture for automated review
tooling. Two endpoints: `/orders?email=` and `/admin/users?email=`.

## Layout

- `src/server.ts` - routes
- `src/auth.ts` - session and admin checks
- `src/db.ts` - order queries
- `src/pool.ts` - connection pool

## Route protection

Every route is wrapped by `withSession`, which rejects any request that does not
carry a valid session cookie before the handler body runs.

## Running locally

Set `PGHOST`, `PGDATABASE`, `PGUSER` and `PGPASSWORD`, then `npm start`.
