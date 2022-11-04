<h1> Jandres Profile <h1/>


<h2 align ="left"> 📈 Activity Graphs</h2>

![](http://github-profile-summary-cards.vercel.app/api/cards/stats?username=Jandres1420&theme=2077)
![](http://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Jandres1420&theme=2077)

![](http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Jandres1420&theme=2077)

![](http://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Jandres1420&theme=2077)

![](http://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Jandres1420&theme=2077&utcOffset=8)
</h2>

## Performance

![][![Anurag's github stats](https://github-readme-stats.vercel.app/api?username=Jandres1420)](https://github.com/anuraghazra/github-readme-stats)

## Comandos Docker

#### Construir imagen
```
docker build --tag dockersparkprimer .
```
#### Mapear puertos
```
docker run -d -p 34002:6000 --name firstdockercontainer3 dockersparkprimer
```
#### Union instancias contenedores
```
docker-compose up -d
```
#### Referencia local docker imagen
```
docker tag dockersparkprimer dnielben/firstsprkwebapprepo
```
#### Push al repo en docker (antes hacer login)
```
docker push dnielben/firstsprkwebapprepo:latest
```
#### Cambiar nombre repositorio (opcional)
```
docker tag primer-docker-spark:latest dnielben/primersparkweb:latest
```
## AWS
```
sudo yum update -y
```
```
sudo yum install docker
```

```
sudo service docker start
```
```
sudo usermod -a -G docker ec2-user
```
```
docker run -d -p 42000:6000 --name firstdockerimageaws dnielben/firstsprkwebapprepo
```
#### Dockerfile:
```
FROM openjdk:8

WORKDIR /usrapp/bin

ENV PORT 6000

COPY /target/classes /usrapp/bin/classes
COPY /target/dependency /usrapp/bin/dependency

CMD ["java","-cp","./classes:./dependency/*","co.edu.escuelaing.sparkdockerdemolive.SparkWebServer"]
```

#### docker-compose.yml:
``` YML
version: '2'


services:
  web:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: web
    ports:
      - "8087:6000"

  db:
    image: mongo:3.6.1
    container_name: db
    volumes:
      - mongodb:/data/db
      - mongodb_config:/data/configdb
    ports:
      - 27017:27017
    command: mongod

networks:
  red1:
    driver: bridge

volumes:
  mongodb:
  mongodb_config:
  ```
  
  #### POM:
  
   ``` XML
  <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>edu.escuelaing.arep</groupId>
    <artifactId>Taller4AREP</artifactId>
    <packaging>jar</packaging>
    <version>1.0-SNAPSHOT</version>

    <name>Taller4AREP</name>
    <url>http://maven.apache.org</url>
    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>8</maven.compiler.source>
        <maven.compiler.target>8</maven.compiler.target>
    </properties>
    <dependencies>
        <dependency>
            <groupId>com.sparkjava</groupId>
            <artifactId>spark-core</artifactId>
            <version>2.9.2</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>3.8.1</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-simple</artifactId>
            <version>1.7.32</version>
            <scope>compile</scope>
        </dependency>
        <dependency>
            <groupId>org.mongodb</groupId>
            <artifactId>mongodb-driver</artifactId>
            <version>3.0.4</version>
        </dependency>
    </dependencies>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-dependency-plugin</artifactId>
                <version>3.0.1</version>
                <executions>
                    <execution>
                        <id>copy-dependencies</id>
                        <phase>package</phase>
                        <goals><goal>copy-dependencies</goal></goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
 ```

