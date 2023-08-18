# docker-all-commands
Docker all commands real time using
 1  yum install docker -y
    2  docker --version
    3  docker version
    4  systemctl start docker.service
    5  systemctl status docker.service
    6  docker version
    7  docker images
    8  docker pull ubuntu
    9  docker images
   10  docker run ubuntu
   11  docker ps -a
   12  docker run --name raham ubuntu
   13  docker ps -a
   14  docker run -it --name raham ubuntu
   15  docker run -it --name radika ubuntu
   16  docker ps -a
   17  docker commit radika img1
   18  docker images
   19  docker run -it --name radika2 img1
   20  history

Day-2

 1  yum install docker -y
    2  systemctl start docker
    3  systemctl status docker
    4  vim Dockerfile
    5  cat Dockerfile
    6  docker images
    7  docker build -t swiggy:v1 .
    8  docker images
    9  docker run -it --name cont1 swiggy:v1
   10  vim Dockerfile
   11  vim raham.txt
   12  ll
   13  vim index.html
   14  ll
   15  vim Dockerfile
   16  cat Dockerfile
   17  docker build -t swiggy:v1 .
   18  vim Dockerfile
   19  docker build -t swiggy:v1 .
   20  docker images
   21  docker run -it --name cont2 swiggy:v1
   22  cat Dockerfile
   23  vim Dockerfile
   24  docker build -t swiggy:v1 .
   25  docker run -it --name cont3 swiggy:v1
   26  ll
   27  rm -rf Dockerfile
   28  vim Dockerfile
   29  docker build -t swiggy:v2 .
   30  docker run -it --name cont4 swiggy:v2
   31  docker ps -a
   32  docker start cont4
   33  docker ps -a
   34  docker attach cont4
   35  vim Dockerfile
   36  docker build -t swiggy:v2 .
   37  docker run -itd --name cont5 swiggy:v2
   38  docker ps -a
   39  docker attach cont5
   40  docker start cont5
   41  docker attach cont5
   42  docker exec cont5 bash
   43  docker start cont5
   44  docker exec cont5 bash
   45  docker ps -a
   46  docker run -itd --name cont6 swiggy:v2
   47  docker run -it --name cont7 swiggy:v2
   48  docker ps -a
   49  vim Dockerfile
   50  docker build -t raham:v1 .
   51  docker run -it --name cont8 raham:v1 /bin/bash
   52  docker run -it --name cont9 raham:v1
   53  cat Dockerfile
   54  vim Dockerfile
   55  docker build -t raham:v2 .
   56  docker run -it --name cont10 raham:v1
   57  docker run -it --name cont10 raham:v2
   58  docker run -it --name cont11 raham:v2
   59  cat Dockerfile
   60  docker ps -a
   61  ll
   62  rm -rf *
   63  docker ps -a
   64  docker rm 72d3fb8de707
   65  docker ps -a
   66  docker stop $(docker ps -a -q)
   67  docker rm $(docker ps -a -q)
   68  docker ps -a
   69  docker images
   70  docker rmi cb4d40c89571
   71  docker rmi -f $(docker images -q)
   72  docker images
   73  vim Dockerfile
   74  ll
   75  vim index.html
   76  docker build -t paytm:m1
   77  docker build -t paytm:m1 .
   78  docker image
   79  docker images
   80  docker run -d --name movies -p 80:80 paytm:m1
   81  vim index.html
   82  docker build -t paytm:t1 .
   83  docker run -d --name train -p 81:80 paytm:t1
   84  vim index.html
   85  docker build -t paytm:c1 .
   86  docker run -d --name train -p 82:80 paytm:c1
   87  docker run -d --name cricket -p 82:80 paytm:c1
   88  docker ps -a
   89  docker images
   90  docker rmi ubuntu
   91  docker images
   92  docker inspect cricket
   93  docker inspect cricket | grep -i Images
   94  docker inspect cricket | grep -i image
   95  docker images
   96  docker history paytm:c1
   97  history 
Day -3

  1  yum install docker -y
    2  systemctl start docker
    3  systemctl status docker
    4  vim Dockerfile
    5  docker build -t raham:v1 .
    6  docker images
    7  docker run -it --name cont1 raham:v1 /bin/bash
    8  docker ps -a
    9  docker run -it --name cont2 --volumes-from cont1 --privileged=true ubuntu
   10  docker ps -a
   11  docker attach cont1
   12  docker run -it --name cont3 -v /volume2 ubuntu
   13  docker run -it --name cont4 --volumes-from cont3 --privileged=true ubuntu
   14  docker images
   15  docker ps -a
   16  docker volume ls
   17  docker volume create raham
   18  docker volume ls
   19  docker volume inspect raham
   20  cd /var/lib/docker/volumes/raham/_data
   21  ll
   22  touch java{1..10}
   23  ll
   24  cd
   25  docker run -it --name cont5 --mount source=raham,destination=/raham ubuntu
   26  cd /var/lib/docker/volumes/raham/_data
   27  ll
   28  cd
   29  docker volume ls
   30  docker inspect 0bd5623c8a220acf8b7fdd5b4498b15d3feb69bc35e575a8f5bf61e295d3680b
   31  cd /var/lib/docker/volumes/0bd5623c8a220acf8b7fdd5b4498b15d3feb69bc35e575a8f5bf61e295d3680b/_data
   32  ll
   33  cd
   34  cd /home/ec2-user/
   35  ll
   36  ls -al
   37  touch local{1..5}
   38  ll
   39  docker run -it --name cont6 -v /home/ec2-user=/xyz ubuntu
   40  docker run -it --name cont7 -v /home/ec2-user:/xyz ubuntu
   41  cd
   42  docker volume ls
   43  docker volume craete abc
   44  docker volume create abc
   45  docker volume create def
   46  docker volume create ghi
   47  docker volume ls
   48  docker volume rm def
   49  docker volume ls
   50  docker volume prune
   51  docker container prune
   52  docker images prune
   53  docker images
   54  docker attach cont1
   55  docker images
   56  docker ps -a
   57  docker volume ls
   58  docker system df
   59  docker system df -v
   60  docker attach cont1
   61  docker system df -v
   62  docker commit cont1 raham:v2
   63  docker system df -v
   64  docker run -it --name cont8 raham:v2
   65  docker system df -v
   66  docker attach cont8
   67  docker images
   68  docker pull jenkins/jenkins:lts
   69  docker images
   70  docker run -it --name ciserver jenkins/jenkins -p 8080:8080
   71  docker run -it --name ciserver jenkins/jenkins:lts -p 8080:8080
   72  docker run -it --name ciserver1 jenkins/jenkins:lts -p 8080:8080
   73  docker run -it --name ciserver1 -p 8080:8080 jenkins/jenkins:lts
   74  docker ps -a
   75  docker container prune
   76  docker run -it --name ciserver1 -p 8080:8080 jenkins/jenkins:lts
   77  docker ps -a
   78  docker run -it --name cont9 ubuntu
   79  docker run -it --name cont10 ubuntu
   80  docker ps -a
   81  docker container prune
   82  docker search jenkins
   83  history
Day -4 

 1  docker swarm init --advertise-addr 172.31.38.45
    2  docker node ls
    3  docker images
    4  vim Dockerfile
    5  vim index.html
    6  docker build -t raham:v1 .
    7  docker ps -a
    8  docker images
    9  docker service create --name raham --replicas 3 --publish 80:80 raham:v1
   10  docker ps -a
   11  docker service create --name raham --replicas 3 --publish 80:80 nginx
   12  docker service create --name raham --replicas 3 --publish 81:80 nginx
   13  docker service ls
   14  docker ps -a
   15  docker service ls
   16  docker service raham scale=10
   17  docker service scale raham=10
   18  docker ps -a
   19  docker service ls
   20  docker service rm hzp9n0obwvqm
   21  docker service ls
   22  docker ps -a
   23  docker service ls
   24  docker stop $(docker ps -a -1)
   25  docker stop $(docker ps -a -q)
   26  docker kill $(docker ps -a -q)
   27  docker ps -a
   28  docker service create --name swiggy --replicas 3 --publish 80:80 nginx
   29  docker ps -a
   30  docker stop 0159e80510a7
   31  docker ps -a
   32  docker kill f00859b9fc25
   33  docker ps -a
   34  docker ps
   35  docker service ls
   36  docker service scale swiggy=10
   37  docker ps -a
   38  docker ps
   39  docker stop 001012580d0e
   40  docker ps
   41  docker service ls
   42  docker service inspect swiggy
   43  docker service inspect swiggy --output yaml
   44  docker service inspect swiggy --output
   45  docker service inspect swiggy --output text
   46  docker service logs swiggy
   47  docker ps -a
   48  docker service ls
   49  docker service ps swiggy
   50  docker service ls
   51  docker service create --name zomato --replicas 5 --publish 81:80 httpd
   52  docker service ls
   53  docker service rm zomato
   54  docker ps
   55  docker service rm swiggy
   56  docker node ls
   57  docker service create --name zomato --replicas 5 --publish 81:80 httpd
   58  docker node ls
   59  docker node rm u89rkpb23a6wu1l51b6d4nhsj
   60  docker node ls
   61  docker node rm w87djp4bsgu8o2ngxxmu2elbz
   62  docker node rm 8qlu23c1ajiixqn4f1u0obto5
   63  docker node ls
   64  docker node rm uaayff3b8aqfvcdleegw3dx82
   65  docker node rm uaayff3b8aqfvcdleegw3dx82 --force
   66  docker node ls
   67  docker swarm join-token manager
   68  docker node ls
   69  docker images
   70  docker tag raham rahamshaik
   71  /
   72  docker tag raham rahamshaik/devopsbyraham
   73  docker tag raham:v1 rahamshaik/devopsbyraham
   74  docker images
   75  docker push rahamshaik/devopsbyraham
   76  docker login
   77  docker push rahamshaik/devopsbyraham
   78  docker images
   79  docker rmi rahamshaik/devopsbyraham
   80  docker images
   81  docker pull rahamshaik/devopsbyraham:latest
   82  docker images
Day-5

 1  yum install docker -y
    2  sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    3  sudo chmod +x /usr/local/bin/docker-compose
    4  sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
    5  docker-compose --version
    6  systemcctl start docker
    7  systemctl start docker
    8  systemctl status docker
    9  vim docker-compose.yml
   10  vim Dockerfile
   11  vim index.html
   12  docker build -t paytrain:v1 .
   13  vim index.html
   14  docker build -t paymovie:v1 .
   15  vim index.html
   16  docker build -t paycric:v1 .
   17  docker images
   18  vim docker-compose.yml
   19  cat docker-compose.yml
   20  docker ps -a
   21  docker-compose up -d
   22  vim docker-compose.yml
   23  docker-compose up -d
   24  docker ps -a
   25  vim docker-compose.yml
   26  cat docker-compose.yml
   27  docker-compose up -d
   28  docker image
   29  docker images
   30  vim docker-compose.yml
   31  docker-compose up -d
   32  docker ps -a
   33  docker-compose up -d --scale=5
   34  docker-compose up -d train --scale=5
   35  docker-compose train --scale=5
   36  docker-compose scale
   37  docker-compose --scale
   38  docker-compose --scale help
   39  docker-compose scale movie=2
   40  docker ps -a
   41  docker-compose logs
   42  docker-compose images
   43  docker-compose ps
   44    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
   45    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
   46
   47  amazon-linux-extras install java-openjdk11 -y
   48  yum install git jenkins -y
   49  systemctl start jenkins
   50  systemctl status jenkins
   51  vim /lib/systemd/system/docker.service
   52  systemctl daemon-reload
   53  service docker restart
   54  chmod 777 /var/run/docker.sock
   55  docker ps -a
   56  ll
   57  docker-compose up -d
   58  docker ps -a
   59  docker-compose ps
   60  docker-compose stop
   61  docker-compose kill
   62  docker-compose ps -a
   63  ll
   64  mv docker-compose.yml docker-compose1.yml
   65  ll
   66  docker-compose up -d
   67  docker-compose -f docker-compose1.yml up -d
   68  docker-compose -f docker-compose1.yml stop
   69  docker-compose -f docker-compose1.yml images
   70  docker-compose images
   71  docker-compose -f docker-compose1.yml images
   72  docker-compose -f docker-compose1.yml up -d
   73  '
   74  ll
   75  mv docker-compose1.yml docker-compose.yml
