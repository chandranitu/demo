https://www.codejava.net/frameworks/spring-boot/user-registration-and-login-tutorial

our MySQL connection id is 8
Server version: 8.0.26 MySQL Community Server - GPL


create database test;

create table users (
        id bigint not null auto_increment,
        email varchar(45) not null,
        first_name varchar(20) not null,
        last_name varchar(20) not null,
        password varchar(64) not null,
        primary key (id) ) ;


INSERT INTO users (id, email,first_name, last_name,password) VALUES (1, 'chandra@test.com','chandra','k', 'test1234');



-------------------------------

https://kubernetes.io/docs/home/    ## reading


https://www.codejava.net/frameworks/spring-boot/user-registration-and-login-tutorial
https://www.javaguides.net/2019/08/registration-login-example-using-springboot-spring-data-jpa-hibernate-mysql-thymeleaf.html



docker build -t logindocker .

docker run -d --name logindocker -p 8080:8080  logindocker 



minikube addons enable ingress

kubectl apply -f tomcat.yml
kubectl apply -f tomcatservice.yml
kubectl apply -f tomcatingress.yml

kubectl expose deployment tomcat-pod --port=80 --target-port=8080 --type LoadBalancer

kubectl exec -it tomcat-pod bash  --namespace=monitoring  -- sh                                                   ## container prompt
minikube kubectl -- exec --stdin --tty --namespace=monitoring tomcat-pod bash

kubectl cp --namespace=monitoring "/home/hadoop/demo/target/demo-0.0.1-SNAPSHOT.jar" tomcat-pod:"/usr/local/tomcat/webapps/"  #copy into pod

kubectl describe service tomcatservice  --namespace=monitoring

kubectl delete -f tomcat.yml
kubectl delete -f tomcatservice.yml


########################################
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
http://localhost:9000
username admin/admin123
########################################################################################################
