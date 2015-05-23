##MySQL##

    USE `schema`;
    TRUNCATE TABLE `table_name`;
    ALTER TABLE `table_name` AUTO_INCREMENT = 1;
    
clean a talbe, but keep the schema (without using `DROP TABLE`)

log in:

    mysql -u <UserName> -p

enter password after prompt.


    show databases;

    mysqldump -u DBUSERNAME -pDBPASSWORD DBNAME > /PATH/backup.sql


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

