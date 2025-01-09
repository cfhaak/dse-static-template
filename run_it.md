## Setup

### If you - for whatever reason - happen to use Windows please
1. [get some JDK in case you haven't already](https://www.java.com/en/download/)
2. make sure ```JAVA_HOME``` environment variable is set correctly
3. [download apache-ant (zip)](https://ant.apache.org/bindownload.cgi)
4. unzip ant to some $path
5. add that $path as ```ANT_HOME``` to windows environment variables (make sure to link the parent folder of the bin subfolder)
6. add ```%ANT_HOME%\bin``` to the ```PATH``` environment variable
7. run ```ant -v``` to check if it worked (it might be necessary to reopen cmd/poweshell/whatever to make sure the changes applied)
8. anyway consider using linux


### If you use Linux
try ```ant -v```, it should already be installed. If not, get it via apt, pacman or whatever you are using.

### If you use MacOs
maybe it's already installed maybe it isn't. Try ```ant -v```. If it isnt't installed try via brew or whatever. Is that port thing still being used? ```sudo port install apache-ant```