# How to self host PlanarAlly for some RPG fun with friends.
This guide aims to walk you through the process of setting up a server with a dockerized version of nginix, let's encrypt and [PlanarAlly](https://github.com/Kruptein/PlanarAlly) so that you can run your own instance of the amazing virtual tabletop software created by [Kruptein](https://github.com/Kruptein).

Before we begin make sure to have:
* a server with a static IP (a CX11 from [Hetzner](https://www.hetzner.com/cloud) works really well for 3.04€/month)
* a domain with full control on your DNS records (if you need to buy one I suggest [Gandi.net](https://www.gandi.net/) and [Porkbun](https://porkbun.com/))

The instructions in this page are ready for a quick copy and paste session in an **Ubuntu 18.04** environment, but should work in every Linux environment (you'd just need to adjust them a little in some cases).

## Part One - Installing Docker and Docker-compose
First of all we need to install the tools we'll be using to put everything in place.

Let's refresh the repositories and make sure we have everything in place to install Docker:
```
sudo apt update && sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Now let's add Docker's GPG key...
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

... and its repository:
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

Ok, now let's update our repositories and install Docker:

```
sudo apt update && sudo apt install docker-ce
```

To check if everything went well you can run this command and see docker running on your system:  

```
sudo systemctl status docker
```

We're almost there! Docker is up and running on our server, we just need to install Docker Compose, a nice utility that will help us in the next steps. Let's download Docker Compose binaries and put them into /usr/local/bin folder:

```
sudo curl -L https://github.com/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```

Now give them the right permissions:

```
sudo chmod +x /usr/local/bin/docker-compose
```

And here we go: **Docker** and **Docker Compose** are ready to be used on our server!

## Part Two - Setting up Let's Encrypt and Nginix


## Part Three - Setting up PlanarAlly
