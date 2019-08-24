# Flyway Sample

## Steps:
1. Download, extract and install Flyway by adding it to PATH (creating symbolic link)
    1. In the folder that you want Flyway installed in, run ```$ wget -qO- https://repo1.maven.org/maven2/org/flywaydb/flyway-commandline/6.0.0/flyway-commandline-6.0.0-linux-x64.tar.gz | tar xvz && sudo ln -s `pwd`/flyway-6.0.0/flyway /usr/local/bin```
1. Make sure you have Java installed
1. Make sure you have Postgres installed
1. Create a Postgres database named "flyway"
    1. Run `$ sudo -u postgres psql`
    1. Run `$ CREATE DATABASE flyway;`
1. Deploy the database migration
    1. Run ```$ flyway -locations=filesystem:/`pwd`/sql/ migrate```
    1. Alternatively, you could put the database migration scripts in {PATH_TO_FLYWAY}/sql/ so that you don't need the locations parameter -- instead you could simply run `$ flyway migrate`
    1. Besides that, you could also put the content of flyway.conf in {PATH_TO_FLYWAY}/conf/flyway.conf instead of creating another flyway.conf file locally, which would enable you to run migrations not only from the current directory, but from anywhere you want
1. Check the database
    1. Run `$ sudo -u postgres psql`
    1. Run `$ \c flyway`
    1. Run `$ \dt`
    1. Run `$ SELECT * FROM person;`
