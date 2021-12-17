# Build application based on mySQL and Wordpress
In this repository we will run a simple application by using Docker Compose Technique. The idea is to run mySQL and Wordpress containers together.

### Create database service 
we create the database service as **db** by using the umage **mysql:latest**:
```
db: 
    image: mysql:latest 
    environment: 
      MYSQL_ROOT_PASSWORD: mypassword 
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpressuser
      MYSQL_PASSWORD: wordpress
    volumes: 
      - db_data:/var/lib/mysql
    restart: always
```

### Create Wordpress service
We create after that the wordpress service based on the **wordpress:latest** image:
```
wordpress:
    depends_on:
      - db
    image: wordpress:latest
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpressuser
      WORDPRESS_DB_PASSWORD: wordpress
``` 

### Run containers from docker-compose file
```
docker-compose up -d
```
You can verify that wordress container is successfully running by visiting `localhost:8080/wordpress`.

### Stop containers
```
docker-compose down
```
