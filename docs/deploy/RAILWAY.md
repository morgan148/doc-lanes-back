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

- DATABASE_URL
- REDIS_URL
- JWT_SECRET
- COOKIE_SECRET
- STORE_CORS
- ADMIN_CORS
- AUTH_CORS
- PORT (provided automatically by Railway) 8080

## Notes / Gotchas
- App **will return 502** if the server listens on the wrong port.
- Railway UI may show "Running" even if the app is unreachable.
- Health check endpoint: GET /health
    Should return HTTP 200.

## Known-Good Git State
- **Tag:** Known-good
- **Commit:** 2c1245a  