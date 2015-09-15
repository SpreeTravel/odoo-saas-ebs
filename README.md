# Odoo Saas on *EBS*

This repository contains the **Docker** configurations needed to
deploy the *cenitsaas/cenitodoo* **Docker** image on **Amazon
Elastic Beanstalk** webservice.

# Steps to deploy
1. Fork the repository.
2. Clone it.
3. Edit the *Dockerrun.aws.json* file and change
  + The **name** (optional)
  + The values of the environment variables **MAIN_DOMAIN** and
    **SERVER_SUBDOMAIN** so they point to your domain names for
    the *portal* and *server* respectively.
4. Compress the file with zip so that its resultant name is
*Dockerrun.aws.json.zip*.
5. Go to your **EBS** workspace and launch a new *application*
or *environment*.
  + Select *web server tier*
  + When prompted for the application upload the zip file just
  created.
  + Instruct the wizard to launch a new **RDS** instance with the
  environment.
    - For the **RDS** instance select a *PostgreSQL* server.
6. With your DNS provider (**GoDaddy** or **Amazon Route 53**)
create *CNAME* rules so that your **MAIN_DOMAIN** and
**SERVER_SUBDOMAIN** point to the url you selected for the
environment (something like xxxxxx.*elasticbeanstalk.com*) unless
your **MAIN_DOMAIN** matches xxxxxx.*elasticbeanstalk.com* and
**SERVER_SUBDOMAIN** is a subdomain of **MAIN_DOMAIN**.
