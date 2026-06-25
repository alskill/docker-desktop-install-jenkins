# docker-desktop-install-jenkins

If Jenkins Is NOT Installed

Pull the Jenkins image:
```bash
docker pull jenkins/jenkins:lts
```
Check:
```bash
docker images
```
You should see:
```bash
jenkins/jenkins   lts
```
Create Jenkins Volume
```bash
docker volume create jenkins-data
```
Start Jenkins:
```bash
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins-data:/var/jenkins_home jenkins/jenkins:lts
```
If Jenkins container exists but is stopped

Start it:
```bash
docker start jenkins
```
Check:
```bash
docker ps
```
Then get the password

In Git Bash, use:
```bash
docker exec -it jenkins bash
```
Inside the container:
```bash
cat /var/jenkins_home/secrets/initialAdminPassword
```
Open Jenkins

Go to:
```bash
http://localhost:8080
```
Then:

Paste the password.
Click Install Suggested Plugins.
Create an admin user.















