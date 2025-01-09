## What is this?
* This is a slightly simplified test template of [DSE-Static-Cookiecutter](https://github.com/acdh-oeaw/dse-static-cookiecutter).
* This isn't intended for production use! Rather use [DSE-Static-Cookiecutter](https://github.com/acdh-oeaw/dse-static-cookiecutter) for this purpose.
* This is a template repository, if you don't know what this means, feel free to [read this](https://github.blog/developer-skills/github/generate-new-repositories-with-repository-templates/) or just click ```Use this template``` (top left corner). It probably does what you expect.

## Local Setup
follow the steps provided in the [documentation for the local setup](./run_it.md)

## Publish the Website
If you want to publish your website **keep in mind that there are some legal requirements for websites, you might need to fulfill (e.g. Offenlegungspflicht gemäß § 25 Mediengesetz, DSGVO etc. if you are based in Austria).** It is your responsibility, to make sure everything is taken care of. If you follow the next steps, your page will be publicly available via the internet.
1. In the github online interface navigate to workflows.
2. On the left select ```Deploy static content to Pages```
3. At the right click on ```Run workflow``` and confirm by clicking on ```Run workflow``` in the dropdown. Your workflow should run now. If the workflow fails check the output for troubleshooting.
4. To check the result, select ```Settings``` in the top navbar, then click on ```Pages``` at the left hand s   ide. In the top panel, your pages url and status can be seen. It might e.g. be necessary to configure the data source manually, by selecting ```GitHub Actions``` from the dropdown under ```Source``` if the build failed.