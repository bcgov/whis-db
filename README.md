![Lifecycle: Maturing](https://img.shields.io/badge/Lifecycle-Maturing-007EC6)

## Wildlife Health Information System (WHIS)

Minimal Postresql 12 and PostGIS 3.0 Docker setup.

### Downloading and Building
```bash
git clone https://github.com/bcgov/whis-db.git
cd whis-db
docker build --tag whis-db:1.0 .
```

### Running Locally
If you have environment variables currently set for the database environment you can do the following. Otherwise substitute in your configuration.
```bash
docker run \
  --publish 5432:5432 \
  --detach \
  --name whis-db \
  --env POSTGRES_PASSWORD=$POSTGRES_PASSWORD \
  --env POSTGRES_USER=$POSTGRES_USER \
  --env POSTGRES_DB=$POSTGRES_DB \
  whis-db:1.0
```

Now you can connect locally.
```bash
psql -h localhost -p 5432 $POSTGRES_DB $POSTGRES_USER
```

## OpenShift ##

OpenShift details including build, deployment and pipelines are in the [openshift](openshift/README.md) folder.
