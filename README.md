# Hello World Spring Boot

A simple Spring Boot application demonstrating CI/CD with Jenkins, Docker, and AWS deployment.

## 🚀 Quick Start

### Installations in EC2 instance
```bash
# Connect to EC2 instance
ssh -i your-key.pem ubuntu@your-ec2-public-ip

# Update system packages
sudo apt update

# Install Java 17
sudo apt install openjdk-17-jdk -y

# Install Jenkins
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y

# Start Jenkins service
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

### API Endpoint
```bash
curl http://localhost:8080/
# Returns: "Hello World from Spring Boot"
```

## 🔄 Pipeline Flow

1. **Code checkout from GitHub** - Pull latest code
2. **Build using Maven** - Compile and package application
3. **Create Docker image** - Build container image
4. **Push image to Docker Hub** - Publish to registry
5. **Run container on EC2** - Deploy to AWS EC2

## 🐳 Docker Image

👉 [Docker Hub](https://hub.docker.com/r/nakshatragowda/hello-world-springboot)

## 🌐 Application URL

**http://[EC2-PUBLIC-IP]:8081**


## 🛠️ Development Setup

```bash
# Clone repository
git clone https://github.com/NakshatraGowda/hello-world-springboot.git
cd hello-world-springboot/demo

# Build and run
mvn clean package
java -jar target/demo-0.0.1-SNAPSHOT.jar
```

## 🏗️ Tech Stack

- **Spring Boot 2.7.18** - Web framework
- **Java 17** - Runtime
- **Maven** - Build tool
- **Docker** - Containerization
- **Jenkins** - CI/CD
- **SonarQube** - Code quality
- **AWS EC2** - Deployment

## 📁 Project Structure

```
├── demo/
│   ├── src/main/java/com/example/hello_world/
│   │   ├── HelloWorldApplication.java
│   │   └── HelloWorldController.java
│   ├── src/test/java/com/example/hello_world/
│   │   ├── CheckHTTPResponse.java
│   │   └── HelloWorldApplicationTests.java
│   ├── Dockerfile
│   └── pom.xml
├── Jenkinsfile
└── README.md
```

## 📞 Contact

**Nakshatra Gowda** - [@NakshatraGowda](nakshatra.gowda.2000@gmail.com)

---