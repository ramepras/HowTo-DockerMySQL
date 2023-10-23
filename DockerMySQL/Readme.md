# How to install MySQL on docker?

## Create a network to communicate all container with network name rather than IP.
    docker network create dev-network

# Command to install MySQL
    docker run --name mysql --net dev-network -v /Users/rame/Documents/Work/Docker/MySQL:/var/lib/mysql -p 3306:3306 -d -e MYSQL_ROOT_PASSWORD=mysql mysql --lower_case_table_names=1

# Connect to MySQL from host.
    docker exec -it mysql bash
    mysql -uroot -p
    (enter password)

# Alter root password to mysql.
    ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'mysql';
    FLUSH PRIVILEGES;
    GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;

# Create your user.
    CREATE USER 'ram'@'%' IDENTIFIED BY 'mysql';
    GRANT ALL PRIVILEGES ON *.* TO 'ram'@'%' WITH GRANT OPTION;
