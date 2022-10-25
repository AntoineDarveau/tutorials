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

![](images/pycharm_remote_and_package_development/step11.png)

- You can access you ssh remotes in the Preferences
![](images/pycharm_remote_and_package_development/see_remotes.png)

## 2. Sync with remote

### 2.1 Update the python interpreter
To be able to run and keep files on the remote in sync, you need too specify the remote interpreter (again) and the remote project.

a. Go in Preferences, then Python interpreter

![](images/pycharm_remote_and_package_development/step12.png)

![](images/pycharm_remote_and_package_development/step13.png)

b. Choose an existing ssh interpreter (you  just created in [Step 1](#1-create-an-empty-project))

![](images/pycharm_remote_and_package_development/step14.png)

![](images/pycharm_remote_and_package_development/step15.png)

c. Then you need to re-specify the python interpreter in the remote server (same as in [Step 1](#1-create-an-empty-project))

![](images/pycharm_remote_and_package_development/step17.png)

![](images/pycharm_remote_and_package_development/step18.png)

d. And the project directory on the remote host.

![](images/pycharm_remote_and_package_development/step19.png)

![](images/pycharm_remote_and_package_development/step20.png)

### 2.2 Setup the deployment server
You need to specify (again...) which directory and server will be used to sync your project.

a. Go in the menu bar, select Tools | Deployment | Configuration

![](images/pycharm_remote_and_package_development/step22.png)

b. Select the correct server with the options you want.
 * Note that you can set the root path to your home directory. Easier for navigation.

![](images/pycharm_remote_and_package_development/step23.png)

c. Set the correct mapping (again) between your local pycharm project and the remote directory

![](images/pycharm_remote_and_package_development/step24.png)

Notes
 * You can change the name of the deployment server for clarity
![](images/pycharm_remote_and_package_development/rename.png)


 
