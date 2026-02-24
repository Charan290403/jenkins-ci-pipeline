```markdown
# 🚀 Flask CI/CD Project using Jenkins & Docker

This project demonstrates a complete CI pipeline using Jenkins running inside Docker.  
The pipeline builds a Flask application into a Docker image and pushes it to DockerHub automatically.

---

## 📌 Project Architecture

GitHub → Jenkins → Docker Build → DockerHub

---

## 🛠 Tech Stack

- Python (Flask)
- Docker
- Jenkins
- DockerHub
- GitHub

---

## 📂 Project Structure

```

flask-ci-project/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
└── README.md

```

---

## 🐳 Docker Setup

### Build Image Manually

```

docker build -t charanb123/flask-ci:v1 .

```

### Run Container

```

docker run -p 8090:8080 charanb123/flask-ci:v1

```

Open:

```

[http://localhost:8080](http://localhost:8080)

```

---

## ⚙️ Jenkins Setup

Jenkins runs inside Docker using Docker Compose.

### Run Jenkins

```

docker compose up -d

```

Access Jenkins:

```

[http://localhost:8090](http://localhost:8090)

```

---

## 🔐 DockerHub Authentication

DockerHub authentication is handled using:

- DockerHub Access Token
- Jenkins Credentials Binding

Credentials ID used in pipeline:

```

dockerhub-cred

```

---

## 🔄 CI Pipeline Stages

1. Checkout Code
2. Build Docker Image
3. Login to DockerHub
4. Push Docker Image

Images are versioned using Jenkins build number.

Example:

```

charanb123/flask-ci:5

```

---

## 🎯 How It Works

- Developer pushes code to GitHub.
- Jenkins pipeline is triggered.
- Docker image is built.
- Image is pushed to DockerHub automatically.
- Image can be deployed anywhere.

---

## 🚀 Future Improvements

- Add GitHub webhook auto trigger
- Add unit testing stage
- Add Kubernetes deployment
- Deploy on AWS EC2

---

## 👨‍💻 Author

Charan  
DevOps & Cloud Enthusiast 🚀
```

---

