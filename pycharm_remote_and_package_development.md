# How to use pycharm to contribute to multiple git repositories
This includes:
- Using git on different repositories, but in the same pycharm project
- Having non-shared (not tracked by git) code to test or just analyse data
- Bonus: running the code on remote servers (niagara in this case)
  
## 1. Create an empty project
a. Go in the menu bar and select File/New Project...

![](images/pycharm_remote_and_package_development/step01.png)


b. Define a remote interpreter (if you want to work remotely).  
You can also choose the name of the project. Here it will stay `pythonProject`.

![](images/pycharm_remote_and_package_development/step02.png)

c. Define the remote server (in this case, narval at compute canada).  
Notes:
 * For astro.umontreal.ca servers, use the port 5822.
 * You need to change `adb` for your own Username.

![](images/pycharm_remote_and_package_development/step03.png)

 * If the server is already defined, select an existing one.

![](images/pycharm_remote_and_package_development/step03b.png)

d. You will get some messages if the connection worked. Simply click `Next`.

![](images/pycharm_remote_and_package_development/step04.png)
![](images/pycharm_remote_and_package_development/step05.png)

e. Specify the location of the remote interpreter.  
Notes:
 * I recommend to install the python environment on the server beforehand.  
 See [this tutorial](https://docs.alliancecan.ca/wiki/Python/fr#Cr.C3.A9er_et_utiliser_un_environnement_virtuel) for more info about Compute Canada environment creation.  So select `Existing` environment.
 
![](images/pycharm_remote_and_package_development/step08.png)
 
 * Trick to find the location of the environment:  
 Connect to the server on a terminal, activate the environment and type `which python`. In the example screenshot below,  you need to replace the `~` by `/home/your_user_name`
 
![](images/pycharm_remote_and_package_development/step07.png)
 
 To find the correct location, you can write it directly or browes the remote files.
 
![](images/pycharm_remote_and_package_development/step09.png)

Finally, click on create to confirm. It will check if it can find the interpreter.

![](images/pycharm_remote_and_package_development/step10.png)

Your project is created!

### Additional notes
- You can switch between interpreters at will. For example, you may want a local interpreter in case your connexion is not working. It can also be useful to be able to work on different servers. To do so, just select or add the interpreter at the bottom of the pycharm window.



## 2.
 
