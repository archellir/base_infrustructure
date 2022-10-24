# base_infrastructure

Infrastructure for base server

#### For postgreSQL multiple databases scripts:

```sh
chmod +x scripts/create-multiple-postgres-databases.sh
```

#### Database backup & restore:

Backup:

```sh
docker exec -t <postgres-container-id> pg_dumpall -c -U <user> > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql
```

Restore:

```sh
cat <dump_name>.sql | docker exec -i <postgres-container-id> psql -U <user>
```
