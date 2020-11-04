# Docker + Rails + Postgresql

* Ruby version - 2.7.2

* Ruby on Rails version - 6

* Database - postgresql

## Create new project

* `git clone --depth=1 --branch=master git@github.com:eddiefisher/rails_bootstrap.git . && rm -rf ./dirformynewrepo/.git`

* `docker-compose run --rm --no-deps runner rails new . --force --database=postgresql`

* change config/database.yml
  ```
  default: &default
    adapter: postgresql
    encoding: unicode
    host: postgres
    username: postgres
    password: password
    pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  ```

* `docker-compose run --rm runner rake db:create`

* `docker-compose run --rm runner rake db:migrate`
