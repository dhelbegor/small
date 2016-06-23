S M A L L
=========
  
  
This is a small example how use docker on systems 32 bits.  

Why this?, because my computer don't suporte 64 bits distributions. /cry ;(  
  
  
Then how WTF use this ....?  
```bash
$ sudo apt-get install docker.io  
$ sudo docker -v  # if all it's ok, you will see something like this: Docker version 1.6.2  
```
  
Next step ...  
  
create a random folder and follow the steps:  
```bash
$ mkdir some_folder  
$ cd some_folder  
$ git clone https://github.com/dhelbegor/small.git  
$ cd small  
```
 
build image:  
```bash
$ sudo docker build -f $(pwd)/docker/Dockerfile -t container_name . # (container_name) some name for your container   
```
  
run this image and enter into bash:  
```bash
$ sudo docker run -ti -v $(pwd)/:/root -p 8000:8000 container_name bash # (container_name) your container name defined on build  
```
  
now go to folder root/:  
```bash
$ cd root/  
$ django-admin.py startproject some_name .  
```

now run project:  
```bash
$ python manage.py runserver 0.0.0.0:8000  
```
  
outside of bash, edit the project:  
```bash
$ sudo subl .  # Why I need use sudo?, because this is defined on build and run remember? $(pwd)/:/root  
```
  
i hope this is helpful :D  
