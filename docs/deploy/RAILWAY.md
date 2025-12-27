# Railway Deployment – doc-lanes-back

## Service
- **Service name:** doc-lanes-back
- **Environment:** Production
- **Region:** us-west2
- **Public URL:** https://doc-lanes-back-production.up.railway.app

## Networking
- **Public port:** 8080  
- **Important:** Railway injects `$PORT` at runtime.  
  The Medusa server **must listen on `$PORT`**, not a hardcoded value.

## Start Command (Railway) npx medusa db:migrate && cd .medusa/server && npx medusa start

## Node Version
- **Node:** 20.x (defined in package.json `engines`)

## Required Environment Variables
> Values are stored in Railway. Do NOT commit secrets.

ADMIN_CORS="https://doc-lanes-front.vercel.app"
AUTH_CORS="https://doc-lanes-front.vercel.app,http://localhost:8000"
CACHE_REDIS_URL="${{Redis.REDIS_URL}}"
COOKIE_SECRET=*****
DATABASE_URL="${{Postgres.DATABASE_URL}}"
DB_NAME="medusa-v2"
JWT_SECRET=**********
PORT=8080
REDIS_URL="${{Redis.REDIS_URL}}"
STORE_CORS="https://doc-lanes-front.vercel.app"


## Notes / Gotchas
- App **will return 502** if the server listens on the wrong port.
- Railway UI may show "Running" even if the app is unreachable.
- Health check endpoint: GET /health
    Should return HTTP 200.

## Known-Good Git State
- **Tag:** Known-good
- **Commit:** 2c1245a  