# Deploying a subfolder to GitHub Pages
Sometimes you want to have a subdirectory on the `master` branch be the root directory of a repository’s `gh-pages` branch.

For the sake of this example, let’s pretend the subfolder containing your site is named `_site`.

## Create a new repository
  * Create a new repository

	> [!NOTE]
	> Do not initialise with any files (readme.md etc.)

  * On PC, Open Git Bash or Sommand Prompt
  * Navigate to your local project
  * Add `.gitignore` file to root of project and add `html` output directory

	```bash
    echo "_site" >> .gitignore
    ```

    > [!NOTE]
    > this will stop the upload of the `web` directory to `master` branch (no point in having html pages in master)

  * Add any additional folders within your project to `.hitignore` you do not want uploading to git branch
  * Initialise git

	```bash
    $ git init
    ```

  * Add project folder (excluding `_site`) to version control

	```bash
	git add .
    ```

  * Add a first commit to version control/git

	```bash
    $ git commit -m "first commit"
    ```

    > [!NOTE]
    > When using `git commit -m "first commit"` each change will have the same message "first commit". You may want to commit each file separately with a different commit message

  * Prepare local project for upload to git

    ```bat
    $ git remote add origin https://github.com/JimBobUKII/my_knowledgebase.git
    ```

    > [!NOTE]
    > this is the `url` to the git repository you created above

  * Push your project up to git in `master` branch

    ```bat
    $ git push -u origin master
    ```

  * Check your git repository, confirm the upload has completed
  * Check on git, you only have `master` branch

## Setting up subfolder fir GitHub Pages
  * Make sure git knows about your subtree (the subfolder with your site).

    ```bat
    $ git add -f _site && git commit -m "Initial _site subtree commit"
    ```

    > [!NOTE]
    > `-f` is only required if you added web folder to `.gitinore`

  * push subtree to the gh-pages branch on GitHub.

    ```bat
    $ git subtree push --prefix _site origin gh-pages
    ```

  * On GitHub, refresh you'r repository and check `gh-pages` branch has been created
  * Select `gh-pages` branch and confirm the directory holds your web data

## Retrieving GitHub Pages site URL
  * Within your git repository, select `Settings`
  * On `options` page, scroll down to `GitHub Pages` section

    > [!NOTE]
    > you should see a message with the url to the published site
    > ***example***: Your site is published at https://GIT_NICKNAME.github.io/REPOSITORY_NAME/

  * Navigate to the published site, confirm the correct site has been published

## Commit to master & gh-pages
### Commit to master
  * within Git Bash, initialise git

    ```bat
    $ git init
    ```

  * Add any additional pages to version control

    ```bat
    $ git add .
    ```

  * Add a first commit to version control/git

    ```bat
    $ git commit -m "first commit"
    ```

    > [!NOTE]
    > When using `git commit -m "first commit"` each change will have the same message "first commit". You may want to commit each file separately with a different commit message

  * Push your project up to git in `master` branch

    ```bat
    $ git push -u origin master
    ```

  * Check your git repository, confirm the upload has completed

### Commit to gh-pages
  * push subtree to the gh-pages branch on GitHub.

    ```bat
    $ git subtree push --prefix _site origin gh-pages
    ```

    > [!NOTE]
    > When using `git commit -m "first commit"` each change will have the same message "first commit". You may want to commit each file separately with a different commit message

# Tube
> [!Video https://www.youtube.com/embed/TAaG0nUUy6A]

# **PowerShell** File
[!code-powershell[Main](test.ps1)]



















