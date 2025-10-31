🧪 Assignment 7 — To Understand Docker Architecture and Deploy a Container
🎯 Goal

Install Docker, understand container lifecycle, and deploy an NGINX container.

⚙️ Steps

Pull the official NGINX image

docker pull nginx


Run the container

docker run -d -p 8081:80 --name mynginx nginx


-d → detached mode

-p 8081:80 → map host port 8081 → container port 80

--name mynginx → container name

Check running containers

docker ps


Open in browser
👉 http://localhost:8081

✅ You’ll see the “Welcome to NGINX!” page.

(Optional) Stop and remove

docker stop mynginx
docker rm mynginx

✅ Result

NGINX container ran successfully, confirming correct installation and understanding of Docker architecture & lifecycle.

🧩 Assignment 8 — Build a Simple Web App Image Using Dockerfile
🎯 Goal

Create a Docker image for a sample web application using a Dockerfile and deploy it.

⚙️ Steps

Create project folder

C:\docker-webapp


Create an HTML file
index.html

<h1>Hello from my Docker Web App!</h1>
<p>This page is served from a Docker container 🚀</p>


Create a Dockerfile
(or Dockerfile.txt if needed — use -f option when building)

FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80


Build the image

docker build -t my-web-app -f Dockerfile.txt .


(Use just Dockerfile if that’s the exact name.)

Run container on a new port (8082)

docker run -d -p 8082:80 --name webapp my-web-app


Check it’s running

docker ps


Open in browser
👉 http://localhost:8082

✅ Shows “Hello from my Docker Web App!”
