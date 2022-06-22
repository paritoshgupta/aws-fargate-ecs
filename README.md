<h1>Container as a Service (CaaS)</h1><br>
![Continuous-Delivery](ECS_workflow.jpg)

- **1. Elastic Container Service**
    - Setup app: virtualenv + make all
    - Test app local: python app.py
    - Curl it to test: curl localhost:8080/change/1/34
    - Create ECR Repo: https://www.freecodecamp.org/news/build-and-push-docker-images-to-aws-ecr/
    - Build container: docker build -t changemachineimage .
    - Push container
        - docker tag changemachineimage:latest XXXXXXXXXX.dkr.ecr.us-east-1.amazonaws.com/changemachine   
        - docker push XXXXXXXXXX.dkr.ecr.us-east-1.amazonaws.com/changemachine   
    - Run docker local: docker run -p 8080:8080 changemachineimage
    - Deploy to Fargate: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html
    - Test the public service

- **2. AWS App Runner**
    