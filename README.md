# php-docker
Docker and PHP build ready to use

Git pull this repository contents

Run: `docker-compose up`

Access application through `localhost` (remove `https://` from URL if added by browser)

# Add MySQL database

To add MySQL database to this build:

Add this line to `Dockerfile`: `RUN docker-php-ext-install pdo_mysql`

Add this container to `docker-compose.yml`: 

    db:
        image: mysql:8.0
        container_name: mysql
        ports:
            - "3306:3306"
        environment:
            MYSQL_ROOT_PASSWORD: root
            MYSQL_DATABASE: root
            MYSQL_USER: project
            MYSQL_PASSWORD: project
        networks:
            - app-network  
