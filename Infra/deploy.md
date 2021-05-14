## EC2 Docker spring - mariadb
```
// git clone project
git clone *address*

// move to backend folder
cd *directory*

// run mariadb, Maria라는 이름의 컨테이너로 3306포트를 사용해 실행. 비밀번호는 본인의 것에 맞게
sudo docker run --name Maria -p 3306:3306 -e MYSQL_ROOT_PASSWORD=1234 -d mariadb

// docker db 접속
sudo docker exec -it Maria mysql -u root -p

// db 생성
create database test_lkw;

// 'net_tmp'라는 이름의 네트워크 생성
sudo docker network create net_tmp

// 'net_tmp'라는 네트워크에 'Maria'라는 컨테이너를 연결
sudo docker network connect net_tmp Maria

// Dockerfile 작성
vim Dockerfile

// application.properties 수정
spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver
spring.datasource.url=jdbc:mysql://Maria:3306/test_lkw
spring.datasource.username=root
spring.datasource.password=1234

// spring build
mvn package

// docker로 빌드
sudo docker build -t springboot .

// 가즈아~
sudo docker run -p 8080:8080 --name Spring --network net_tmp springboot
```

## 참고
user테이블이 없어요!  
https://my.oops.org/195  
docker run 옵션  
https://www.daleseo.com/docker-run/  
