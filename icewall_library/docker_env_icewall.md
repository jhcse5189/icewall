
# **Get Docker Engine - Community for Ubuntu**
    https://docs.docker.com/install/linux/docker-ce/ubuntu/

## SET UP THE REPOSITORY
- - -
>### 1. Update the `apt` package index.
    $ sudo apt-get update

>### 2. Install packages to allow `apt` to use a repository over HTTPS.
    $ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

>### 3. Add Docker's official GPG key.
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

>### 4. Verify that you have the key with the fingerprint,
***9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C*** `0EBF CD88`
by searching for the last 8 characters of it.

    $ sudo apt-key fingerprint 0EBFCD88

    pub   rsa4096 2017-02-22 [SCEA]
          9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
    uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]

>### 5. Use the following command to set up the **stable** repository.

    $ lsb_release -cs
    bionic
    $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"


#


## INSTALL DOCKER ENGINE - COMMUNITY
- - -
>### 1. Update the `apt` package index, **again**.
    $ sudo apt-get update

>### 2-1. Install the *`lastest version`* of Docker Engine.
    
    $ sudo apt-get install docker-ce docker-ce-cli containerd.io

### 2-2. If you want to install a *`specific version`* of Docker Engine, list the available version in repo, and then select and install.

    $ apt-cache madison docker-ce
        
      docker-ce | 5:18.09.1~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
      docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
      docker-ce | 18.06.1~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
      docker-ce | 18.06.0~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
      ...
copy the string of the specific version from the `second column`.

    $ sudo apt-get install docker-ce=5:19.03.2~3-0~ubuntu-bionic docker-ce-cli=5:19.03.2~3-0~ubuntu-bionic containerd.io

### 3. Verifying by running hello-world image.
    $ sudo docker run hello-world
 
- - -
- - -

# **Create a base image**
    https://docs.docker.com/develop/develop-images/baseimages/

## CREATE A FUL IMAGE USING TAR
- - -
>### 1. 