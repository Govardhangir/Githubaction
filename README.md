# Prerequisites
##### ###
- JDK 21
- Maven 3 
- MySQL 8

# Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- Tomcat
- MySQL
- Memcached
- Rabbitmq
- ElasticSearch
# Database
Here,we used Mysql DB 
sql dump file:
- /src/main/resources/db_backup.sql
- db_backup.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < db_backup.sql


## CI/CD Overview
This project uses GitHub Actions for CI/CD.
Pipeline stages:
- Maven Build & Test
- SonarQube Code Quality Scan
- Docker Image Build
- Trivy Security Scan
- Push Image to AWS ECR
- Deploy to Amazon ECS
#