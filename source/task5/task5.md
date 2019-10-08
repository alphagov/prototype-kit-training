# Task 5: uploading to the web

To publish your prototype, you must:

- push your prototype to the remote GitHub repo
- deploy your site on Heroku

For this task, we recommend using the integrated terminal that comes with Visual Studio code.

## Push prototype to GitHub

These instructions assume that you have prototype changes ready to push to GitHub.

To push your prototype changes to GitHub for the first time, you must:

- **create a new repository** (remote) on GitHub
- **initialise the local directory** as a Git repository
- **add** and **commit** your files
- **push the staged commits** to the remote repo

### Create a new repository

Create a remote empty repo in your organisation on GitHub by clicking the **New** in your GitHub account dashboard.

To avoid errors, **do not** initialise the new repository with a README, license or gitignore files. You can add these files after your project has been pushed to GitHub.

![Do not initialise readme](/images/readme.png)

Make sure you make the repo **Public** so anyone can collaborate on it.

When you're done, click **Create repository**.


### Initialise the local directory as a Git repository

1. Go to your juggling license prototype directory using the command line. In Visual Studio code, opening a terminal in the text editor window automatically cd you into your prototype repo.

1. Make the prototype directory into a local Git repo:

    ```
    git init
    ```

### Add and commit your prototype files

1. Add all files in the local repo and stage them for commit:

    ```
    git add .
    ```

1. Commit the staged files:

    ```
    git commit -m "COMMIT-MESSAGE"
    ```

    where `COMMIT-MESSAGE` is the message describing the commit. This is your first commit to the repo so it's fine to replace `COMMIT-MESSAGE` with `first-commit`.


### Push the staged commits to the remote repo

1. Go to the remote repo in GitHub. This is the empty repo created earlier.

1. Select the __Clone or download__ button.

1. Select __Use HTTPS__ .

1. Select the copy button.

1. Back in the command line, link the local repo to the remote repo by typing:

    ```
    git remote add origin REMOTE-REPO-URL
    ```

    Where `REMOTE-REPO-URL` is the copied URL.


### Push the changes to the remote repo

Push the changes in your local repo to the remote repo:

```
git push -u origin master
```

You have now created a remote version of your prototype on GitHub. Go to the remote repo and check that all your files are there.


## Deploy with Heroku

Open [www.heroku.com](https://www.heroku.com/) and log in if you're not already logged in.

In the top right click **New** then **Create new app**

Names in Heroku have to be unique across all the users of Heroku. It can be helpful to add your name or organisation to the start of the name to make it unique. For example **yourname-juggling-prototype**

Select **Europe** for the region - this is not important but makes your prototype a bit faster.

For **deployment method** choose **GitHub**

![Deploy Heroku app using github master branch](/images/heroku-deploy.png)
 
1. Scroll down and click **Connect to GitHub**

2. In the popup, click **Authorize Heroku**

3. In the **repo-name** field, type all or some of your repo name, as it is on GitHub. Click **search**

4. Click **connect** on the right of your repo.

5. Scroll down to the **Manual deploy** section and click **Deploy branch**

### Secure your prototype

One more thing: we need to set a username and password or the prototype won't run online.

At the top click the **Settings** tab

Click **Reveal config vars**

1. In **KEY** put the word USERNAME
2. In **VALUE** put a username of your choice, click Add

That will be saved and you can add another KEY and VALUE

In KEY put the word PASSWORD
In VALUE put a password of your choice, click Add

![Set your app username and password](/images/config-vars.png)

In the top top right, click **Open app** to see your prototype online!