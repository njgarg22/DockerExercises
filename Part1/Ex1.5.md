//To start an ubuntu image 
~ neeraj$ docker run -d --name curlex -it ubuntu:16.04 

//To enter inside the container
~ neeraj$ docker exec -it curlex bash

//Retrieve new lists of packages
root@c4108c16ed7e:/# apt-get update

//Install sudo
root@c4108c16ed7e:/# apt-get install sudo -y

//Install curl
root@c4108c16ed7e:/# sudo apt install curl

//Execute the command and input `helsink.fi` to test
~ neeraj$ docker exec -it curlex sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
