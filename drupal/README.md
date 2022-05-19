
# Install Docker Compose
Download the latest version of Docker Compose. Check the releases page and replace 1.25.4 in the command below with the version tagged as Latest release:

 sudo curl -L https://github.com/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
Set file permissions:

 sudo chmod +x /usr/local/bin/docker-compose

## Set Up Drupal
Create a new directory in your home folder called my_drupal and cd into it:

mkdir ~/my_drupal/
cd ~/my_drupal/
Create a file named docker-compose.yml in this folder and add the following contents. Set your own password for the POSTGRES_PASSWORD option.


## File: docker-compose.yml
From the my_drupal directory, start your Docker containers:

`docker-compose up -d`

