# django-for-heroku
##
This is a base django app with version 1.10.3 that can easily be deployed to Heroku.


### Steps in deploying to Heroku
1. Clone this project to your local machine.
```sh
git clone https://github.com/renzosunico/django-for-heroku.git new-project
```
2. Create a new repository in your github account.
3. Go to directory of cloned folder and delete git folder.
```sh
cd new-project
rm -rf .git
```
4. Initialize a new git repository inside the directory.
```sh
git init
```
5. Set the origin your local git with the newly created  remote repository.
```sh
git remote add origin https://github.com/<YOUR-GIT-REPOSITORY>
```
6. Remove README.md file.
```sh
rm README.md
```
7. Pull remote repository and push all the contents to remote repository.
```sh
git pull origin master
git add .
git commit -am "Initial Project"
git push origin master
```
7. Go to Heroku and create a new app.
8. Deploy the project by connecting your github account to Heroku.
9. Install Heroku-cli.
10. Login to your account.
```sh
heroku login
Email: <Your-heroku-email-address>
Password: <Your-heroku-password>
```
11. Create your .env file in apps/settings directory.

```sh
heroku run bash --app <YOUR-HEROKU-APP-NAME>
echo 'DB_NAME="<DESIRED-DB-NAME>"' >> apps/settings/.env
exit
```
12. Run the migrations.

```sh
heroku run 'python apps.manage.py migrate --settings="settings.production" --app <YOUR-HEROKU-APP-NAME>
```
