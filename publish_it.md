## Publish the Website

While creating a page hosted on your local host is fun and great for development, our goal will probably be to make the page available on the internet. You are going to use GitHub Pages for that purpose, a solution to easily publish (static) websites without having to worry about infrastructure like servers or domain names. When you build the page locally, you have to perform certain actions (like running Ant) before you can see your website. To automate these steps when building the page online, GitHub provides so-called workflows. As the name suggests, it's a (rather ugly) way to describe workflows step by step. In our case, we are going to use a workflow called [Deploy static content to Pages](./.github/workflows/build.yml) to:

- Set up a virtual machine online that will perform the tasks necessary to generate the page
- Install dependencies (like Ant, etc.)
- Build the page and publish it
- Add other steps later on

If you want to publish your website, **keep in mind that there are some legal requirements for websites** that you might need to fulfill (e.g., Offenlegungspflicht gemäß § 25 Mediengesetz, DSGVO, etc., if you are based in Austria). It is your responsibility to ensure that everything is taken care of. By following the next steps, your page will be publicly available on the internet.

1. To configure the data source GitHub Pages will be using, select **Settings** in the top navbar, then click on **Pages** on the left-hand side. By selecting **GitHub Actions** from the dropdown under **Source**, you tell GitHub Pages to expect data to be coming from an action (rather than from a simple folder containing HTML documents).
2. In the GitHub online interface, navigate to **Workflows**.
3. On the left, select **Deploy static content to Pages**.
4. On the right, click on **Run workflow** and confirm by clicking **Run workflow** in the dropdown. Your workflow should be running now. If the workflow fails, check the output for troubleshooting.
5. To check the result, select **Settings** in the top navbar, then click on **Pages** on the left-hand side. In the top panel, your page's URL and status can be seen.

If you're under the impression that DSE-Static-Cookiecutter creates fewer problems than you try to solve and therefore consider using it in production, it might be worth [checking out the original repository](https://github.com/acdh-oeaw/dse-static-cookiecutter) and following the workflow described there. If you are using Windows, it might be beneficial to run the initialization process in an environment shared with WSL (Windows Subsystem for Linux).
