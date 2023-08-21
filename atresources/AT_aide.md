https://docs.docker.com/engine/reference/commandline/ps/
https://www.hostinger.fr/tutoriels/commandes-git#Git_config
https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-push-an-existing-project-to-GitHub#:~:text=Simply%20issue%20a%20git%20push,the%20git%20push%20command%20accordingly.&text=The%20%2Du%20switch%20makes%20the,default%20for%20your%20existing%20project.
https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-push-an-existing-project-to-GitHub#:~:text=Simply%20issue%20a%20git%20push,the%20git%20push%20command%20accordingly.&text=The%20-u%20switch%20makes%20the,default%20for%20your%20existing%20project.
https://git-scm.com/docs/git-remote

command docker:
https://www.geeksforgeeks.org/remove-all-containers-and-images-in-docker/

https://www.knowledgehut.com/blog/devops/basic-docker-commands
---------------------------------------
SSH
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

https://www.warp.dev/terminus/git-clone-ssh
 ls ~/.ssh
 ssh -T git@github.com
 ssh-keygen -t ed25519 -C “user@example.com”
  eval "$(ssh-agent -s)"
  echo $SSH_AUTH_SOCK
  ssh-add ~/.ssh/id_ed25519
  git config --global credential.helper cache.

  # start the ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid 59566
------------------------------------------
  
  git clone -b master https://github.com/athabti/atapidjango2.git  AT_demo1

  git remote -vv
 git checkout -b demo1_testing
 git checkout -b iss53
 git push -u origin demo1_testing

---------------------------------
pour la mise à jour de ll'apli

docker-compose build

docker-compose run --rm app sh -c "python manage.py wait_for_db python manage.py 
test  &&flake8"
---------------------------------

 docker restart my_container
docker ps --all
docker build .
docker-compose up
docker-compose run --rm app sh -c "flake8"
docker-compose run --rm app sh -c "python manage.py test"

git add .
git commit -am "le 16/08/2023 après correction du gethub sécurity ."
git log
git push origin 
git branch
git checkout "nom de la  brance"
git branch " nom branche"
docker login -u athabti
docker login -u athabti -p dckr_pat_A3UO7w8lg7bW-W1OkBdQHkdWOZs
  username: ${{secrets.DOCKERHUB_USER}}
          password: ${{secrets.DOCKERHUB_TOKEN}}

--------------------------------

docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py test && flake8"
_________________________________
docker-compose -f docker-compose-deploy.yml down
//   -------------------OK----------------
docker-compose -f docker-compose-deploy.yml down
docker-compose -f docker-compose-deploy.yml up
docker-compose run --rm app sh -c "python manage.py createsuperuser" 
docker-compose -f docker-compose-deploy.yml up -d
docker-compose -f docker-compose-deploy.yml run --rm app sh -c "python  manage.py createsuperuser"
admin@example.com
rosnysousbois

 docker-compose -f docker-compose-deploy.yml logs
  docker-compose run --rm app sh -c "python manage.py test"
docker-compose down
docker-compose down --volume
 docker-compose run --rm app sh -c "python manage.py test"
 docker-compose up
 docker-compose run --rm app sh -c "python manage.py test"

 après git pull
 docker-compose -f docker-compose-deploy.yml build app
  docker-compose -f docker-compose-deploy.yml up --no-deps -d app ( reconstruit l'appli sans les composant dependant exemple DB server)
----------------------------------
pour la mise à jour de ll'apli
docker-compose build
docker-compose run --rm app sh -c "python manage.py wait_for_db python manage.py test  &&flake8"
--------------------------------
docker rmi <imageId/Name>
docker rmi -f <imageId/Name>
docker image prune
docker rmi $(docker images -q)
docker stop <containerId/Name>
docker stop $(docker ps -aq)
docker rm  <containerId/Name>
docker rm $(docker ps -aq)
docker rm $(docker ps -aq --filter  status="exited")
  explication filter : filter like status=exited or status=running or
   name and so on

docker stop $(docker ps --filter status=running -q)
docker rm $(docker ps --filter status=exited -q)
docker container prune

push vers dockerhub:
docker tag local-image:tagname new-repo:tagname
docker push new-repo:tagname



--------------------------------------
---
name: Checks

on: [push]

jobs:
  test-lint:
    name: Test and Lint
    runs-on: ubuntu-20.04
    steps:
      - run: echo " This repository is ${{ github.repository }}"
      - name: "verification du setting from git"    
        run: echo " username ${{ secrets.DOCKERHUB_USER }} mot de pass ${{ secrets.DOCKERHUB_TOKEN }}"
        shell: bash
      - name: executer a inline script
        run: |
            mkdir newfolder
            ls -l
        shell: sh
            
      - name: Login to Docker Hub
        uses: docker/login-action@v1
        with:
          username: ${{ secrets.DOCKERHUB_USER }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      - name: Checkout
        uses: actions/checkout@v2
      - name: Test
        run: docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py test"
      - name: Lint
        run: docker-compose run --rm app sh -c "flake8"

    Docker version
Docker search 
Docker pull
Docker run 
Docker ps
Docker stop 
Docker restart 
Docker kill
Docker exec 
Docker login
Docker commit 
Docker push 
Docker network 
Docker history 
Docker rmi 
Docker ps -a
Docker copy
Docker logs   
Docker volume 
Docker logout