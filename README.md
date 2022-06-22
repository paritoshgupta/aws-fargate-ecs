<h1>Container as a Service (CaaS)</h1><br>

![Continuous-Delivery](ECS_workflow.jpg)

- **1. Elastic Container Service Method**
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

- **2. AWS App Runner Method**

    - Build and run production web applications at scale
    - AWS App Runner is a fully managed service that makes it easy for developers to deploy from source code or container image directly to a scalable and secure web application.
    - **AWS App Runner creates a streamlined workflow that connects a source repo, deploy environment, and a resulting secure URL.**
    - This repository can easily be converted to an AWS Runner Method in Wizard to the following:

        - For build do: pip install -r requirements.txt
        - To run: python app.py
        - For port: 8080

![Continuous-Delivery](aws_app_runner.png)

** A key innovation is the ability to connect many different services on AWS, i.e., core infrastructure, like AWS CloudWatch, Load Balancers, Container Services and API gateways into one complete offering.


    