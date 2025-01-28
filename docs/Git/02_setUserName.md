# Setting your username in Git

Git uses a username to associate commits with an identity. The Git username is not the same as your GitHub username.

=== "Windows"
You can change the name that is associated with your Git commits using the git config command. The new name you set will be visible in any future commits you push to GitHub from the command line. If you'd like to keep your real name private, you can use any text as your Git username.

Changing the name associated with your Git commits using git config will only affect future commits and will not change the name used for past commits.

Setting your Git username for every repository on your computer

- [x] Open git bash
- [x] Set a Git username :
  ```
  git config --global user.name "Your Github UserName"
  ```
- [x] Confirm that you have set the Git username correctly:
  ```
  $ git config --global user.name

  ```
> Your UserName


 
=== "Mac"
- [x] Open Mac Terminal
- [x] Set a Git username :
  ```
  git config --global user.name "Your Github UserName"
  ```
- [x] Confirm that you have set the Git username correctly:
  ```
  $ git config --global user.name

  ```
> Your UserName

=== "Linux"
- [x] Open Linux Terminal
- [x] Set a Git username :
  ```
  git config --global user.name "Your Github UserName"
  ```
- [x] Confirm that you have set the Git username correctly:
  ```
  $ git config --global user.name

  ```
> Your UserName
