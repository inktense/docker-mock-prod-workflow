# Docker workflow for a single container production app

This project is a frontend React application that is hosted in a Docker container and deployed to AWS Elastic Beanstalk using GitHub Actions.

## Prerequisites
-----
Before getting started, you'll need to make sure you have the following tools installed:

    - Node.js (version 12 or later) 
    - Docker
    - AWS CLI

You'll also need to create an AWS Elastic Beanstalk application and environment to deploy your application to.

## Installation
-------
To install the project, follow these steps:

1. Clone the repository to your local machine.
2. Run `npm install` to install the project dependencies.
3. Run `docker build -t my-react-app . `to build the Docker image.
4. Run `docker run -p 3000:3000 my-react-app` to start the container.


## Usage
------
Once the Docker container is running, you can access the application by navigating to http://localhost:3000 in your web browser.


## Deployment
------
To deploy the project to AWS Elastic Beanstalk using GitHub Actions, follow these steps:

1. Create an Elastic Beanstalk environment in the AWS Management Console.
2. Configure the AWS CLI on your local machine with your AWS credentials.
3. Create a new IAM user with the AWSElasticBeanstalkFullAccess policy attached, and generate an access key and secret access key.
4. In the GitHub repository, go to Settings > Secrets and add the access key and secret access key as environment variables.
5. Modify the .github/workflows/deploy.yml file to include your AWS region, Elastic Beanstalk application name, and environment name.
6. Push your changes to the main branch of the repository. GitHub Actions will automatically build the Docker image, push it to Amazon ECR, and deploy the application to Elastic Beanstalk.
