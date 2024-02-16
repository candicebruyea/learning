# Docker Basics

Lets you bundle your local dev open environment in isolated containers that are portable.

Your dependencies and configuration for the project are bundled in the container (source code, php version, sql database, web server (apache)).


1. Docker container starts as a simple linux machine, nothing installed.
2. Then we tell the container what needs to be installed (dependencies needed to run the application) - done using a docker file.

## Docker File
a text file where you write instructions on how to build a docker image.

## Docker Image
A read only executable package.
Includes everything needed to run your application:
Source code, dependencies, environment variables, configurations, etc.
Are read only and can exist without containers.

## Container
Need an Image to run. Images are like bases or templates to build your containers. Container is a runtime instance of an image that can now be modified.

## Docker File -- Image -- Container
Images are stored in repositories (public or private). You can then pull those images from repository and use them to build your containers on local, staging, or in production.


# Installing Docker

1. Check docker version using command:

        docker version

2. Download Docker Desktop for Mac. https://docs.docker.com/get-docker/
3. Drag Docker.app file to Applications folder.
4. Double click on application to start Docker engine
    * You should see the Docker icon in the top status bar - if not, Docker is not running.
5. Open terminal and run docker version command again. You should see Client and Server info listed.

# Terminal Commands

List all containers currently running

    docker ps

View a summary of image vulnerabilities and recommendations 

    docker scout quickview drupal

# Installing mysql

1. go to hub.docker.com
2. search mysql official image
3. download it
4. in terminal, run detach mode (-d) 

       docker run -d
5. add mysql image

       docker pull mysql
6. log into docker account

       docker login

7. After getting the image, complete the container setup for mysql 

       docker run -d --name mysqldatabase -e MYSQL_ROOT_PASSWORD=root mysql:latest

8. do docker ps to check that sql image is running

       docker ps


# Drupal setup in Docker

1. go to docker hub and go to drupal official page
2. enter in terminal the docker pull command 


    docker pull drupal
3. complete copntainer setup for drupal


    docker run -d --name drupalcontainer --link mysqldatabase -e MYSQL_USERNAME=root -e MYSQL_PASSWORD=root drupal:latest

3. do docker ps to check that both images are running

 
    docker ps







# Development Workflow Basics

## Add a Dockerfile to your site files (allows you to run it with Docker). 
Contains instructions that Docker uses to package your site into an Image.
* The image contains everything your application needs to run.
  * A cut-down OS
  * A runtime environment (like Node or Python)
  * Application files
  * 3rd party libraries
  * Environment Variables
  * ETC

## Once you have an Image, tell Docker to start a Container using that Image.
Container is a process with its own file system provided by the Image
Our Site gets loaded inside the Container (an isolated environment) locally on our machine.

## Docker Hub
Once our image is registered on Docker hub, we can put it on any machines running Docker.
On the new machine, we just tell Docker to start a Container using that Image.

# Dev Workflow Detailed Steps

## Create The Website 
1. Make a directory for your project.
        
        mkdir hello-docker
2. Go inside the directory

        cd hello-docker
3. Open directory using PHPStorm 

         phpstorm .
4. Create your site files.

## Package the Site using Docker
### Write the instructions for running the site into a Dockerfile
1. Create Dockerfile in PHPStorm, filename: Dockerfile (no extension)
   * PHPStorm might ask to install the recommended extensions for Docker, allow this.
2. Write instructions for packaging the site into the Dockerfile
   * Base Image (official images can be found on Docker Hub)
   * Other stuff (I haven't gone into depth on this subject yet)
3. Tell Docker to package up our site files into an image file.
    * specify a tag for the file with -t
    * specify where docker can find the Dockerfile (. in this case) 

        
         docker build -t hello-docker 
4. To see all Docker images in this directory... 

        docker image ls

## Run the Site Image on any computer using Docker

1. In terminal, run the image using docker run + image name.
   
        docker run hello-docker

24:30

# Sources
"Docker Tutorial for Beginners" *Youtube* @@programmingwithmosh 
[https://www.youtube.com/watch?v=pTFZFxd4hOI](https://www.youtube.com/watch?v=pTFZFxd4hOI)

