# docker-compose-task
The application uses the Flask framework and maintains a hit counter in Redis.

##Prerequisites
- docker installed
- Docker-compose installed
  -if not install using `brew install docker-compose`

##Task

- Clone the Repository 
- Create a docker-compose.yml file
  - Define Services(web and redis) using `services` keyword
  - For web provide build directory which contains Dockerfile and redis - use redis image(redis:alpine)
  - Port forwarding for the Web application
    - web --> 80:5000
  - Add volume mount for the web app , mount the app.py file in the image's working directory
  - Add environment variable `FLASK_ENV: development` with keyword `environment` to see the changes made in code immediately without building image
- Run `docker-compose up`
- Check the running containers `docker ps` or `docker-compose ps`

##Test the App
- Open the localhost port defined in the docker-compose file.
- You should below text 
  ``` 
      Hello World! I have been seen 1 times.
  ```
- Make some text changes in the app.py file, the changes should immediately reflect in the localhost on refresh