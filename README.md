# project_title



* build with [DSE-Static-Cookiecutter](https://github.com/acdh-oeaw/dse-static-cookiecutter)


## initial (one time) setup

* run `./shellscripts/script.sh`

* run `ant`

## set up GitHub repo
* create a public, new, and empty (without README, .gitignore, license) GitHub repo github_code_repo_url 
* run `git init` in the root folder of your application cookiecutter_template
* execute the commands described under `…or push an existing repository from the command line` in your new created GitHub repo github_code_repo_url

## start dev server

* `cd html/`
* `python -m http.server`
* go to [http://0.0.0.0:8000/](http://0.0.0.0:8000/)

## publish as GitHub Page

* go to https://github_code_repo_url/actions/workflows/build.yml
* click the `Run workflow` button


## dockerize your application

* To build the image run: `docker build -t cookiecutter_template .`
* To run the container: `docker run -p 80:80 --rm --name cookiecutter_template cookiecutter_template`
* in case you want to password protect you server, create a `.htpasswd` file (e.g. https://htpasswdgenerator.de/) and modifiy `Dockerfile` to your needs; e.g. run `htpasswd -b -c .htpasswd admin mypassword`

### run image from GitHub Container Registry

`docker run -p 80:80 --rm --name cookiecutter_template ghcr.io/:github_user_name/cookiecutter_template:main`
