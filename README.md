# Docker + Rails + Postgresql

* Ruby version - 2.7.2

* Ruby on Rails version - 6

* Database - postgresql

## Create new project

* `mkdir directory_name && cd directory_name`

* `git clone --depth=1 --branch=main git@github.com:eddiefisher/rails_bootstrap.git . && rm -rf ./.git`

* without react `docker-compose run --rm runner rails new . --force --database=postgresql -T`

* or with react `docker-compose run --rm runner rails new . --force --database=postgresql -T --webpack=react --skip-coffee --skip-turbolinks`

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

* `docker-compose run --rm runner rake db:create db:migrate`

* `docker-compose up web`
