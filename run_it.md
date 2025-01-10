## Setup

### Whatever System you are using
you will need a github account. If you don't already have one, create a new one and come back here.
While being logged into you github account, start by creating a new repository based on this template repository by clicking **Use this template** and **Create a new repository**, if you haven’t done this already.
If you haven't installed python yet, [install it](https://www.python.org/downloads/), you will need it! (Check *add python to path* on windows while installing.)

### If you happen to use Windows please
1. [get some JDK in case you haven't already](https://www.java.com/en/download/)
2. [download apache-ant (zip)](https://ant.apache.org/bindownload.cgi)
3. unzip ant to some $path
4. add that $path as ```ANT_HOME``` via *Edit environment variables for your account* (make sure to link the parent folder of the bin sub folder)
5. add ```%ANT_HOME%\bin``` to the ```PATH``` environment variable
6. run ```ant -v``` to check if it worked (it might be necessary to reopen cmd/powershell/whatever to make sure the changes applied)
7. anyway consider using linux/wsl


### If you use Linux
try ```ant -v```, it should already be installed. If not, get it via apt, pacman or whatever you are using.

### If you use MacOs
maybe it's already installed maybe it isn't. Try ```ant -v```. If it isn't installed try via brew or whatever. If that port thing is still being used: ```sudo port install apache-ant```

## Build page
1. Clone your newly created github repository.
2. Open your favorite terminal. Navigate to the base directory of this repository.
3. Run ```ant```. It will automatically use the [build-file](./build.xml) in this repository to determine what to do.
4. One thing ant does as described in the build-file is essential for building a website: XML files placed in data/editions get transformed to html-files and saved in the [html folder](./html/).
5. If you want to see the resulting page, navigate to the html folder, run a server (depending on your system ```python -m http.server --bind 127.0.0.1``` or ```python3 -m http.server --bind 127.0.0.1```) and check the page in your browser.

## Customize Page
Start by setting the ```project_title``` and the ```project_short_title``` variable in [```./xslt/partials/params.xsl```](./xslt/partials/params.xsl). Try committing and pushing your changes to github. Maybe also change the [README.md](./README.md) containing the text from the template repository.
You can provide your own xml-files by dumping them into ```data/editions``` and you will likely need to customize the xslt scripts in the xslt folder. Also the site needs some css. You could add some bootstrap classes to the xslt or provide your own css.