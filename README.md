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
6. Install `git`
```
sudo yum install git -y
```

7. Create an SSH key and add it to GitHub
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

8. Install nginx
```
sudo amazon-linux-extras install nginx1
```

9. Edit `/etc/nginx/nginx.conf` [(See YouTube)](https://www.youtube.com/watch?v=WmdL8aOVooM)
```
location / {
    proxy_pass http://localhost:5000;
}
```
10. Enable nginx
```
sudo systemctl start nginx.service
```
11. Install `screen`
```
screen -S server
```
To reattach to screen
```
screen -r server
``` 