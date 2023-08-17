https://docs.docker.com/engine/reference/commandline/ps/
https://www.hostinger.fr/tutoriels/commandes-git#Git_config
https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-push-an-existing-project-to-GitHub#:~:text=Simply%20issue%20a%20git%20push,the%20git%20push%20command%20accordingly.&text=The%20%2Du%20switch%20makes%20the,default%20for%20your%20existing%20project.
https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-push-an-existing-project-to-GitHub#:~:text=Simply%20issue%20a%20git%20push,the%20git%20push%20command%20accordingly.&text=The%20-u%20switch%20makes%20the,default%20for%20your%20existing%20project.

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