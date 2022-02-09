https://docs.docker.com/samples/rails/ <br />
docker-compose run --no-deps web rails new . --force --database=postgresql <br />
docker-compose build <br />
Edit config/database.yml change all content with this: <br />
```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password: password
  pool: 5

development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test
```
docker-compose up <br />
docker-compose run web rake db:create
