##MySQL##

    USE `schema`;
    TRUNCATE TABLE `table_name`;
    ALTER TABLE `table_name` AUTO_INCREMENT = 1;
    
clean a talbe, but keep the schema (without using `DROP TABLE`)

log in:

    mysql -u <UserName> -p

enter password after prompt.


    show databases;

    mysqldump -u DBUSERNAME -p DBPASSWORD DBNAME > /PATH/backup.sql

    mysqldump > backup.sql --all-databases -u DBUSERNAME -p


Or:
create `~/.my.cnf` file with the following content:

    [client]
    #comment
    #port=3306
    user = DBUSERNAME
    password = "DBPASSWORD"
    host = localhost

change mode:

    chmod 0600 ~/.my.cnf

Then use:

    mysqldump DBNAME > /PATH/backup.sql


View all users:

    select User from mysql.user;

Drop user:

    drop user UserToRemove;


start:

    service mysqld start

alternatively:

    /etc/init.d/mysqld start