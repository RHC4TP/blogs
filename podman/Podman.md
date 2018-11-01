With the release of Red Hat Enterprise Linux 7.6 (link: http://www.eweek.com/enterprise-apps/red-hat-enterprise-linux-7.6-launches-with-improved-security) , there are several new features being introduced. Once of them, which we think is really cool and helps get our enviorment set up quicker, is a new way to build container image called podman.


## What is Podman?
Podman is a tool designed for managing containers. It does not require a daemon to run containers, and non-root users can benefit from this tool. Which means no more having to give your developers access to root privileges. Podman also implements almost all the Docker CLI commands, therefore there are no new commands to learn. You can still use your existing Dockerfiles. Does using a new tool to get the same job done get much easier than that? 

## Installing Podman  
To install podman run: 

`$ yum install -y podman` 


## Using Podman
If you know how to use Docker CLI, then you know Podman. Just replace *docker* with *podman*. Below are several examples: 

Building an image: 

`$ podman build -t <image_name> <path_to_image_files>`

Example building an image named happy in current directory:

`$ podman build -t happy .`

Running a contianer: 

`$ podman run -d -it -t <image_id> /bin/bash` 


## Certifying your Container with Red Hat Connect
You will need to login to the [Red Hat Connect Portal](https://connect.redhat.com/). Go to your projects page and go to the Upload your Image tab. You will need to login first before tagging and pushing your image. You can change the *docker* command to *podman*. Your Registry Key is the password for your login.

`$ podman login -u unused -e none scan.connect.redhat.com`

Tag your Image. *Please note this is an example, you will need to copy the command located in your project page and change docker to podman*: 

`$ podman tag [image-id] scan.connect.redhat.com/ospid-12345678-9100-abcd-efg-hijklmnopqr/[image-name]:[tag]`

Push your image. *Please note this is an example, you will need to copy the command located in your project page and change docker to podman*: 

`$ docker push scan.connect.redhat.com/ospid-12345678-9100-abcd-efg-hijklmnopqr/[image-name]:[tag]`

Other thing you can do with Podman are:


For more information about what podman can do go to here (link)
