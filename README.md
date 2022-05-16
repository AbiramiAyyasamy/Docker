# Docker
# Docker 101

Module: **Virtualization** </br>
Competency: [is able to use Docker to containerize applications](./evaluation.md) </br>
Duration: **5 days** </br>
Participant(s): **solo** </br>
Output: **comment on issue**

## The mission

Wouldn't it be nice if you could just port applications and services from one device to another without facing the dreaded "_but it worked on my machine_"? That's one of the need [Docker](https://www.docker.com/) is trying to meet, with the promise of **simple portability** through **isolation of processes**.

This challenge will have you explore both the `docker` (_CLI and Dockerfiles_) and `docker-compose` command. The challenge is going to be divided into two sections, one where you'll explore the tool and another where you'll apply what you've learned in a practical example.

Follow the instructions below to get started on the first part:

- Install `docker` on your machine, then follow a [tutorial](https://labs.play-with-docker.com/) (_requires an account_). Make sure you understand the CLI usage as well as how to create your own [images](https://searchitoperations.techtarget.com/definition/Docker-image) with Dockerfiles.
- Install `docker-compose` on your machine, then follow a [tutorial](https://takacsmark.com/docker-compose-tutorial-beginners-by-example-basics/).
- **Practice by containerizing** websites, applications and services you already deployed in the past like the [COGIP](https://github.com/becodeorg/BXL-Lovelace-7.34/issues/94) or a [git server](https://github.com/becodeorg/BXL-Lovelace-7.34/issues/93). You can also deploy new ones, for example coming from this [list](https://github.com/awesome-selfhosted/awesome-selfhosted). **Do this until you feel confortable** with both `docker` and `docker-compose.`

Often times you will have to deploy multiples websites on the same server. Using `containers` makes that process **easy** and **allows for high availability**. Your mission will be to deploy both a [Wordpress](https://wordpress.com/) and a [Drupal](https://www.drupal.org/) website using the following architecture:

- a mysql database containing a tables for both websites 
- a wordpress container 
- a drupal container 
- a reverse proxy container

Follow the instructions below to guide you along.

- Check how to install `Wordpress` and `Drupal` locally and understand how it works 
- Try to run both website individually in `docker containers` with _volume mapping_ and _port redirection_. Try to access it on your localhost to ensure that everything is working
- Once you understand how it works individually, try to make a `docker-compose` file allowing to deploy the full stack. The following services are expected: `Wordpress`, `Drupal`, a `database` and a `webserver`.
- Configure your `webserver` to act as a `reverse proxy`. You should be able to access both websites from different URLs in your local environment (_[subdomain](https://www.wpbeginner.com/glossary/subdomain/#:~:text=A%20subdomain%20is%20an%20additional,store.yourwebsite.com) or subfolder_)
- When you are done, comment on the issue linked to this challenge on your training's repository.

> **NOTE**: A good "_rule of thumb_" when it comes to containerization is that **each process should live in its own container**. As an example, an `Apache` + `PHP` + `MySQL` website should have at least two (_depends if you consider PHP has its own service_) or even three containers (_one for each services_) talking to each other for the required data to work.

## Complementary Resources

* Tuto: [Create your own image](https://docs.docker.com/develop/develop-images/baseimages/)
* Doc: [Docker Compose documentation](https://docs.docker.com/compose/)
* Doc: [Docker documentation](https://docs.docker.com/)
* Doc: [Wordpress documentation](https://codex.wordpress.org/)
* Doc: [Drupal documentation](https://www.drupal.org/documentation)
* Doc: [Nginx reserse proxy](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)
* Webpage: [Apache reverse proxy](https://httpd.apache.org/docs/2.4/howto/reverse_proxy.html)
* Article: [Linux host file](https://vitux.com/linux-hosts-file/)
* Article: [Windows host file](https://www.liquidweb.com/kb/edit-host-file-windows-10/)

## Final words

Although the technology behind `docker` are much older (ex: `cgroups`, `namespaces`), it was the first tool to gain such widespread use and democratize containerization within the tech industry and although alternatives exist (_[podman](https://podman.io/), [Systemd-Nspawn](https://www.freedesktop.org/software/systemd/man/systemd-nspawn.html), ..._) it still dominates when it comes to application containers.

![Briefing's GIF](https://c.tenor.com/z3Vqx6hmE5QAAAAC/whale-docker.gif)
