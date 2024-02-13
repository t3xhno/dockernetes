# Commands

Start the database, with data persistence and authentication:
```bash
docker --rm -d --name bazica --network network-name -v data:/data/db -e MONGO_INITDB_ROOT_USERNAME=tex -e MONGO_INITDB_ROOT_PASSWORD=password mongo
```

Start the backend, with live code update for development, and persistent logs:
```bash
docker --rm -d -v "/full/path/to/backend/dir:/app" -v /app/node_modules -v logs:/app/logs --network network-name --name goals-be -p 80:80 -e MONGODB_USERNAME=tex -e MONGODB_PASSWORD=password goals-be
```

Start the fe, with live code update for development:
```bash
docker --rm -d -v "/full/path/to/frontend/dir/src:/app/src" -v /app/node_modules --network network-name --name goals-fe -p 3000:3000 -it goals-fe
```
