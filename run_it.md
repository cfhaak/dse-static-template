## Setup

Disclaimer: This tutorial was tested thoroughly, but it might still include steps, that could do unexpected harm your system. Using it is on your own risk.

### Things you’ll need:
1. Get yourself a GitHub account. (This isn't necessary for building a website using cookiecutter, but there are parts of this tutorial relying on GitHub.)
2. If you haven't installed python yet, you should download and install it ([e.g. here](https://www.python.org/downloads/)), so that you can run it from your terminal. Make sure to check *add python to path* during installation.
3. If you are not sure how to authenticate with GitHub other then from your browser or you don't know what that means, consider installing [Visual Studio Code](https://code.visualstudio.com/). This is a code editor, which interacts easily with GitHub.
4. A terminal. Depending on your operating system, there is a bunch of alternatives. For our purpose the default ```terminal``` programs will be enough. For Windows users either ```cmd``` or ```powershell``` could be used.

### Get started with GitHub
1. While being logged into you GitHub account, start by creating a new repository based on this template repository by clicking **Use this template** and **Create a new repository** on the [main page of this repository](https://github.com/cfhaak/dse-static-template). Make your new repository *public* by checking the corresponding field. However keep in mind, that this means everything you store in your repository will be public! Make sure to not accidentally expose any sensitive, copyrighted or otherwise problematic data!
2. Clone the repository you just created. ([Here's how to do that using VS Code.](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git#_clone-a-repository-locally) Make sure to select *Clone from Github*.)


### If you happen to use Windows (and don't want use WSL) please
1. [get an up to date Java Runtime Environment (JRE) if you haven't already](https://www.java.com/en/download/)
2. [download apache-ant (zip)](https://ant.apache.org/bindownload.cgi)
3. unzip ant to some path, most common would probably be ```%ProgramFiles%```
4. add that path as ```ANT_HOME``` via *Edit environment variables for your account* (make sure to link the parent folder of the ```bin``` sub folder, could be something like ```%ProgramFiles%/apache-ant-1.10.15-bin\apache-ant-1.10.15```)
5. add ```%ANT_HOME%\bin``` to the ```PATH``` environment variable
6. open a new cmd or powershell terminal
6. run ```ant -v``` to check if it worked. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means, everything works as expected.
7. anyway consider using WSL


### If you’re using Linux
try ```ant -v```, it should already be installed. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist!
Build failed``` This actually means, everything works as expected. If ant isn’t installed for some reason, get it via apt, pacman etc.

### If you’re using MacOs
maybe it's already installed maybe it isn't. Try ```ant -v```. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means, everything works as expected. However if it isn't installed try via installing it via brew etc. If that port thing is still being used ```sudo port install apache-ant``` should install it.

## Build page
1. Open your favorite terminal. Navigate to the base directory of this repository. (You just cloned it, remember?) If you are not sure how to navigate thru the filesystem with your terminal, look it up. In some filebrowser it’s possible to open a context menu (eg. by right-clicking in a folder) and select an option like *open terminal here*.
2. Run ```ant```. It will automatically use the [build-file](./build.xml) in the repository folder, to determine what to do.
3. One thing *ant* does as described in the build-file is essential for building a website: XML files placed in data/editions get transformed to html-files and saved in the [html folder](./html/).
4. If you want to see the resulting page, navigate to the html folder, run a server (depending on your system ```python -m http.server --bind 127.0.0.1``` or ```python3 -m http.server --bind 127.0.0.1```)
5. While your server is running [open the page](https://127.0.0.1) in your browser.

## Customize Page
Start by setting the ```project_title``` and the ```project_short_title``` variable in [```./xslt/partials/params.xsl```](./xslt/partials/params.xsl). Run *ant* again, as you already did above. Try committing and pushing your changes to github. Maybe also change the [README.md](./README.md) containing the text from the template repository.

You could provide your own xml-files by dumping them into ```data/editions``` and you will likely need to customize the xslt scripts in the xslt folder. Also the site needs some css. You could add some bootstrap classes to the xslt or provide your own css.

If you want to get so practice in dealing with xslt and how the page building works, [check out the hands on practice](jobs_en.md).