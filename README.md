# 🚂 Dockerize-RailSathi-code — A Simple Python App

This repository contains a minimal Python application named **RailSathi**, containerized using **Docker** for consistent environment setup and easy deployment across systems.

---

## 📁 Project Structure

```

.
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml (optional)
└── README.md

````



## ⚙️ Technologies Used

- Python 3.x
- Flask (minimal API)
- Docker
- Docker Compose (optional)


## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/RohanDobriyal/Dockerize-RailSathi-code---a-simple-python-code.git
cd Dockerize-RailSathi-code---a-simple-python-code
````



### 2. Create a Virtual Environment (for local testing)

```bash
python3 -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

App will run locally at `http://127.0.0.1:5000`


## 🐳 Docker Instructions

### 1. Build the Docker Image

```bash
docker build -t railsathi-app .
```

### 2. Run the Docker Container

```bash
docker run -p 5000:5000 railsathi-app
```

Now visit: [http://localhost:5000](http://localhost:5000)


## 🐳 Using Docker Compose (Optional)

If using `docker-compose.yml`, you can run:

```bash
docker-compose up --build
```

This will automatically build and run the app on port 5000.


## 🔧 Sample Files

### app.py

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "Welcome to RailSathi - Dockerized Python App!"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```



### requirements.txt

```
flask
```



### Dockerfile

```dockerfile
# Use official Python image
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Copy application files
COPY . .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose port
EXPOSE 5000

# Run the application
CMD ["python", "app.py"]
```



### docker-compose.yml (Optional)

```yaml
version: '3'
services:
  railsathi:
    build: .
    ports:
      - "5000:5000"
```





## 🙋‍♂️ Author

* [Rohan Dobriyal](https://github.com/RohanDobriyal)

---

