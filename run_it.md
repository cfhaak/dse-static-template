# 1. Setup

Disclaimer: This tutorial was tested thoroughly, but it might still include steps that could unexpectedly harm your system. Use it at your own risk.

## Things you’ll need:
1. Get yourself a GitHub account. (This isn't necessary for building a website using cookiecutter, but there are parts of this tutorial that rely on GitHub.)
2. If you haven't installed Python yet, you should download and install it ([e.g. here](https://www.python.org/downloads/)), so that you can run it from your terminal. Make sure to check *Add Python to PATH* during installation.
3. If you are not sure how to authenticate with GitHub other than from your browser, or you don't know what that means, consider installing [Visual Studio Code](https://code.visualstudio.com/). This is a code editor that interacts easily with GitHub.
4. A terminal. Depending on your operating system, there are a bunch of alternatives. For our purposes the default ```terminal``` programs will be enough. For Windows users, either ```cmd``` or ```powershell``` can be used.

## Get started with GitHub
1. While logged into your GitHub account, start by creating a new repository based on this template repository by clicking **Use this template** and **Create a new repository** on the [main page of this repository](https://github.com/cfhaak/dse-static-template). Make your new repository *public* by checking the corresponding field. However, keep in mind that this means everything you store in your repository will be public! Make sure to not accidentally expose any sensitive, copyrighted, or otherwise problematic data!
2. Clone the repository you just created. ([Here's how to do that using VS Code.](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git#_clone-a-repository-locally) Make sure to select *Clone from GitHub*.)

## If you happen to use Windows (and don't want to use WSL) please:
### Java
0. Check if Java is installed. Open cmd, type ```java -version```. If it returns some version, you can skip installing Java. If not,
1. [get an up-to-date Java Runtime Environment (JRE) if you haven't already](https://www.java.com/en/download/). You'll probably need "Windows Offline (64-bit)".
2. Just run the installer after downloading.
### Apache Ant
0. Check if Ant is installed. Open cmd, type ```ant -version```. If it returns some version, you can skip installing Ant. If not,
1. [download Apache Ant (zip)](https://ant.apache.org/bindownload.cgi) (Yes, the page looks confusing. Download the "…bin.zip" file.)
2. unzip the file to the ```C:\Pogram Files\``` folder. If Windows for some reason decides that you shouldn't be able to access this folder on your computer, try to create/use something like ```C:\Users\YourUsername\bin\```
3. Open *Edit environment variables for your account* by simply searching for it via the search option of the Windows menu. (No, this isn't the same as "Edit the system environment variables".)
4. Find the ```PATH``` variable in the list. Select it and click ```edit```.
5. Choose *new* and paste the path of the ```bin``` folder inside the Ant folder you just unzipped. It likely looks something like this: ```C:\Program Files\apache-ant-1.10.15-bin\apache-ant-1.10.15\bin```
6. Open a new cmd or PowerShell terminal.
7. Run ```ant -v``` to check if it worked. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means everything works as expected.

## If you’re using Linux
Try ```ant -v```, it should already be installed. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist!
Build failed``` This actually means everything works as expected. If Ant isn’t installed for some reason, get it via apt, pacman, etc.

### If you’re using macOS
Maybe it's already installed; maybe it isn't. Try ```ant -v```. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means everything works as expected. However, if it isn't installed, try installing it via brew, etc. If MacPorts is still being used, ```sudo port install apache-ant``` should install it.

# 2. Building and Running

## Build page
1. Open your favorite terminal. Navigate to the base directory of this repository. (You just cloned it, remember?) If you are not sure how to navigate through the filesystem with your terminal, look it up. In some file browsers it’s possible to open a context menu (e.g., by right-clicking in a folder) and select an option like *open terminal here*.
2. Run ```ant```. It will automatically use the [build-file](./build.xml) in the repository folder to determine what to do.
3. One thing *Ant* does, as described in the build-file, is essential for building a website: XML files placed in data/editions get transformed to HTML files and saved in the [html folder](./html/).
4. If you want to see the resulting page, navigate to the html folder, run a server (depending on your system ```python -m http.server --bind 127.0.0.1``` or ```python3 -m http.server --bind 127.0.0.1```)
5. While your server is running [open the page](https://127.0.0.1) in your browser.

## Customize Page
Start by setting the ```project_title``` and the ```project_short_title``` variable in [```./xslt/partials/params.xsl```](./xslt/partials/params.xsl). Run *Ant* again, as you already did above. Try committing and pushing your changes to GitHub. Maybe also change the [README.md](./README.md) containing the text from the template repository.

You could provide your own XML files by dumping them into ```data/editions``` and you will likely need to customize the XSLT scripts in the xslt folder. Also, the site needs some CSS. You could add some Bootstrap classes to the XSLT or provide your own CSS.

If you want to get some practice in dealing with XSLT and how the page building works, [check out the hands-on practice](jobs_en.md).
