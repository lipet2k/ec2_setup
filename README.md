# Template Setup for AWS EC2 Instances

1. Create an EC2 instance on Amazon AWS (make sure `https` and `http` permissions are on)
2. Choose AWS 2 AMI
3. Install Docker
```
sudo yum update -y
sudo yum install -y docker

sudo service docker start

sudo usermod -a -G docker ec2-user
```
4. Log out and log back in
5. Install docker-compose and use the test `docker-compose.yaml` file
```
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose version
```

