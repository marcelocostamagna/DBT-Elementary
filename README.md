# DBT-Elementary
DBT for transformation &amp; Elementary for running data tests

## Create Postgres DB service
```bash
docker compose up -d
```

## Install dependencies
```bash
poetry install --no-root
```

## Run materializations and test
Warning: **profiles.yml** shouldn't be exposed, this is just an example :-)
```bash
cd marc_shop
export DBT_PROFILES_DIR=./
```

```bash
poetry run dbt deps
poetry run dbt seed
poetry run dbt run --select elementary
poetry run dbt run
poetry run dbt test
```

## Shut down Postgres DB service
```bash
docker compose down -v
```

## Pre-commit tools
### pre-commit hooks (run all of them)
```bash
poetry run pre-commit install
poetry run pre-commit run --all-files
```

### Run only Sqlfluff
```bash
poetry run sqlfluff lint
```

## More Info
- More data tests available at [`DBT Test Hub`](https://www.elementary-data.com/dbt-test-hub)
- Elementary  [`official documentation`](https://docs.elementary-data.com/introduction)
