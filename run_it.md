## Setup

### If you - for whatever reason - happen to use Windows please
1. [get some JDK in case you haven't already](https://www.java.com/en/download/)
2. make sure ```JAVA_HOME``` environment variable is set correctly
3. [download apache-ant (zip)](https://ant.apache.org/bindownload.cgi)
4. unzip ant to some $path
5. add that $path as ```ANT_HOME``` to windows environment variables (make sure to link the parent folder of the bin sub folder)
6. add ```%ANT_HOME%\bin``` to the ```PATH``` environment variable
7. run ```ant -v``` to check if it worked (it might be necessary to reopen cmd/poweshell/whatever to make sure the changes applied)
8. anyway consider using linux


### If you use Linux
try ```ant -v```, it should already be installed. If not, get it via apt, pacman or whatever you are using.

### If you use MacOs
maybe it's already installed maybe it isn't. Try ```ant -v```. If it isn't installed try via brew or whatever. If that port thing is still being used: ```sudo port install apache-ant```

## Build page
1. Clone this repo.
2. Open your favorite terminal. Navigate to the base directory of this repo. Run ant.
3. XML files placed in data/editions get transformed to html-files and saved in the html folder. You can provide your own files and customize the xslt scripts in the xslt folder.
4. If you want to see the resulting page, navigate to the html folder, run an server (```python -m http.server --bind 127.0.0.1```) and check the page in your browser

## Publish page
You can easily publish the  page online via github pages. Just configure the permissions and run the workflow.

### Keep in mind that publishing a website might require you to provide information satisfying certain legal requirements. (Eg. DSGVO/Offenlegungspflicht)