## Set Up WordPress
Create a new directory in your home folder called my_wordpress and cd into it:

<pre class="terminal">
mkdir ~/my_wordpress/
cd ~/my_wordpress/
</pre>

Create a file named docker-compose.yml in this folder and add the following contents. Set your own passwords for the WORDPRESS_DB_PASSWORD, MYSQL_ROOT_PASSWORD, and MYSQL_PASSWORD environment options. The password entered for WORDPRESS_DB_PASSWORD and MYSQL_PASSWORD should be the same.


## File: docker-compose.yml
From the my_wordpress directory, start your Docker containers:

`docker-compose up -d`

The Docker containers will take a minute or two to start up WordPress and MySQL. Afterwards, you can visit your Linode’s IP address in your web browser and you should be directed to the WordPress setup form.

Usage and Maintenance
You do not need to manually start your containers if you reboot your Linode, because the option restart: always was assigned to your services in your docker-compose.yml file. This option tells Docker Compose to automatically start your services when the server boots.

To stop your WordPress application:

<pre class="terminal">
cd ~/my_wordpress/
docker-compose down
</pre>

When a Docker container is stopped, it is also deleted; this is how Docker is designed to work. However, your WordPress files and data will be preserved, as the docker-compose.yml file was configured to create persistent named volumes for that data.

If you want to remove this data and start over with your WordPress site, you can add the --volumes flag to the previous command. This will permanently delete the WordPress posts and customizations you’ve made so far.

docker-compose down --volumes
Update WordPress
The docker-compose.yml specifies the latest version of the WordPress image, so it’s easy to update your WordPress version:

<pre class="terminal">
docker-compose down
docker-compose pull && docker-compose up -d
</pre>
