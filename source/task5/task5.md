# Task 5: uploading to the web

To publish your prototype, you must:

- push your prototype to the remote GitHub repo
- deploy your site

## Push prototype to GitHub

These instructions assume that you have prototype changes ready to push to GitHub.

To push your prototype changes to GitHub for the first time, you must:

- create local and remote GitHub repos
- commit all changes in the local repo
- link the local repo to the remote repo
- push the staged commit to the remote repo

### Create local and remote GitHub repos

[Create a remote empty repo](https://help.github.com/articles/create-a-repo/) in your organisation on GitHub.


### Commit all changes in the local repo

1. Go to the local repo directory in the command line.

1. Make the created local repo into a Git repo:

    ```
    git init
    ```

1. If applicable, add all files in the local repo and stage them for commit:

    ```
    git add .
    ```

1. Commit the staged files:

    ```
    git commit -m "COMMIT-MESSAGE"`
    ```

    where `COMMIT-MESSAGE` is the message describing the commit.

### Link the local repo to the remote repo

1. Go to the remote repo in GitHub.

1. Select the __Clone or download__ button.

1. Select either __Use HTTPS__ or __Use SSH__.

1. Select the copy button.

1. In the command line, link the local repo to the remote repo:

    ```
    git remote add origin REMOTE-REPO-URL
    ```

1. Verify the remote repo:

    ```
    git remote -v
    ```

### Push the staged commit to the remote repo

Push the changes in your local repo to the remote repo:

```
git push -u origin master
```

You have now created a remote documentation repo on GitHub.

For more information, refer to [Adding an existing project to GitHub](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/).

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