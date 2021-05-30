# springboot-application

# Pre-Requisites:
    - Install nginx
    - Install git
    - Install maven
# Install nginx using below comamnds
    amazon-linux-extras install nginx1 -y
  ````Start nginx service````
    
    service nginx start
  ````check status````
    
    service nginx status
# Install git
    yum install git -y
# Install maven
    yum install maven -y
# Clone springboot application
    git clone https://github.com/Naresh240/nginx-reverse-proxy-for-springboot-application.git
# Build artifact
    cd nginx-reverse-proxy-for-springboot-application
    mvn clean install
# Deploy springboot applicaiton using with ````nohup```` command
    nohup java -jar target/gs-spring-boot-0.1.0.jar > springboot.log &
# Check Output of springboot applicaiton
    curl http://localhost:8080
# Replace ````nginx.conf```` file at ````/etc/nginx/nginx.conf````
    rm -rf /etc/nginx/nginx.conf
    mv nginx.conf /etc/nginx/nginx.conf
# Restart nginx service
    service nginx restart
# Open 80 port number in security group and check output of springboot application
    http://52.5.196.234/
    
# If you want to do secure with https, need to purchase domain, need to add certificates in ````/etc/nginx/nginx.conf````
