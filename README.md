# PostgreSQL-12 and pgAdmin4

## How to install on Ubuntu 20.04

source: https://wiki.postgresql.org/wiki/Apt
```terminal
#Import the repository key from https://www.postgresql.org/media/keys/ACCC4CF8.asc: 
$ sudo apt-get install curl ca-certificates gnupg
$ curl https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

#Create /etc/apt/sources.list.d/pgdg.list. The distributions are called codename-pgdg.
#TO avoid erros at apt update add arch=amd64
$ sudo sh -c 'echo "deb [arch=amd64] http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

$ sudo apt update
$ sudo apt install postgresql-12 pgadmin4
```

## How to connect to cli psql

```terminal
$ sudo -i -u postgres

#U should be logged in as postgres@user
$ psql
```

## Setting a password for the postgres user for use in other applications

```terminal
postgres=# ALTER USER postgres PASSWORD 'myPassword';
ALTER ROLE

#If successful, Postgres will output a confirmation of ALTER ROLE as seen above.
```