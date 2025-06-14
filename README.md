# Teachbook Editor test in the TeachBooks template

The template allows you to test the TeachBook Editor: 

![image](https://github.com/user-attachments/assets/506238db-2ec7-4241-86d7-3ab20f14e799)


## How to get started

How to use the template is demonstrated in the figure below, all steps are elaborated on in the following step-by-step tutorial.

1. To get started, use the [template TeachBook](https://github.com/TeachBooks/main/template) as template:

![Use template](https://github.com/TeachBooks/template_figures/blob/main/use_template.png?raw=true)

2. Fill in a repository name, this name will be used in the future url of your book:

![Create new repository](https://github.com/TeachBooks/template_figures/blob/main/create_new_repository.png?raw=true)

3. You need to activate GitHub pages so that your website is published to the internet. As long as you don't do this your TeachBook is not published online. Actually, now that you've taken this template our workflow tries to publish it to GitHub pages, which you didn't have the chance to activate yet. That's why you probably received an email with 'call-deploy-book: Some jobs were not successful' and you see the failed job under `Initial commit`. You can activate GitHub pages by setting the source for GitHub pages to GitHub Actions under `Settings` - `Pages` - `Build and deployment` - `Source` - `GitHub Actions`:

![Activate GitHub Pages](https://github.com/TeachBooks/template_figures/blob/main/set_up_pages.png?raw=true)

4. Change the baseurl and repository_url properties in `_config.yml` under html and html_theme_options to `https://<your_username>.github.io/<your_repository_name>/` and `https://github.com/<your_username>/<your_repository_name>` respectively. The end result should look like this:

```yaml
html:
      favicon : "figures/TB_favicon.ico"                 # Replace this with your own favicon
      baseurl : "https://<your_username>.github.io/<your_repository_name>/"
...
html_theme_options:
      logo:
...
      repository_url: "https://github.com/_<your_username>_/_<your_repository_name>_"
```

5.  Now checkout the progress of the publishing workflow under `Actions` - `All workflows` -  `call-deploy-book` -`<the most recent workflow run>`. Remember, the first commit which is there has failed because GitHub Pages wasn't activated at the time of `Initial commit`.

6. When the workflow has finished, visit your built TeachBook at `https://<username or organiszation_name>.github.io/<repository_name>` (case sensitive). For our example it is [https://dummydocent.github.io/test_book_from_template/](https://dummydocent.github.io/test_book_from_template/) for the shown repository. These links are visible in the action's summary as well, as shown in the figure of step 4.

7. Generate a personal access token, go to https://github.com/settings/personal-access-tokens/new. Give it a recognizable name. Under repository access, either set all repositories, or select the repository you just made for your TeachBook. Under Permissions > Repository permissions, set the 'contents' option to read and write. Then, click on generate token. You can copy and paste this token into the application, but you can only do this once. When you close that page, the token will be gone. Treat the token like you would any password.

8. To test the TeachBooks editor, click the 'edit page' button on the top of a page in your built book
