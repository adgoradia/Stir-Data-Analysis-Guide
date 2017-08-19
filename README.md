# Data Analysis with R and MongoDB

**Installations**
1. Installing RStudio
2. Installing Git
3. Installing MongoDB
4. Installing Studio3T
5. Installing OpenVPN

**Connections**
1. Connecting to OpenVPN
2. Connecting to MongoDB database through Studio 3T
3. Importing data from MongoDB database to RStudio into a dataframe

**Experimenting with Data in R**
1. Viewing Dataframes
2. Basic commands, syntax, etc.
3. Creating graphs
4. Searching through data

**What I need to work on**
1. Creating a plot with # of venues in each city and showing a percentage of specials to venues



# Installing RStudio
To work with data in R, we will use the RStudio IDE, a free and open-source software. R is a free software environment for statistical computing and graphics, and it is extremely useful for providing valuable insights and experimenting with data. RStudio can be downloaded [here](https://www.rstudio.com/products/rstudio/download/).

###### Notes:
######  - When downloading RStudio, make sure to download the RStudio Desktop Version that is compatible with your computer. For example, if your laptop/desktop is a 32-bit machine, then download the 32-bit RStudio Desktop Version that corresponds with your operating system (Mac OSX/Windows). Similarly, if your computer is a 64-bit machine, then download the corresponding 64-bit version.
######  - RStudio includes a text editor, so you don't have to install another stand-alone editor (If you prefer a stand-alone editor, my top recommendations would be Komodo Edit and/or Atom)
######  - RStudio also includes an interface to Git and GitHub. You will need to install Git (covered in the next section), but RStudio provides a basic GUI for interacting with Git and GitHub.

Once you have downloaded RStudio and followed the steps listed in the installer, you will notice that RStudio is organized into 4 main sections: The Shell (top left), Console (bottom left), Global Environment (top right), and the Viewer (bottom right).
  - The Shell is where code is written. Althought the console can be used to write code, the Shell is much more convenient and organized. Additional dataframes and files that are opened will show up as tabs on the Shell.
  - The Console outputs the code that you run, along with any errors and messages. When your code is running, a "stop" sign will show up on the top right corner of the console. The signal to knowing when to run any lines of code is the blue ">" sign on the console. When this symbol shows up, it means the console is ready for any additional lines of code that can be prompted.
  - The Global Environment contains two tabs: Environment and History. The Environment tab showcases all of the variables in your code (i.e. dataframes, arrays, integers, iterators, etc.). Furthermore, if you click the "Global Environment" dropdown button, you will be able to see a list of all the packages and libraries that your project is using. The History tab displays a log of all the commands you ran in your project.
  - The Viewer has multiple functions, as shown by the available tabs. The "Files" tab displays all the files in your directory, the "Plots" tab displays any plots that you create, and the "Packages" tab displays a list of all the available packages in R with a short description of each one's function.
  
 
# Installing Git
To work with MongoDB data and various libraries in R, we will use Git, an extremely useful version control system. If you are a graphic or web designer and want to keep every version of an image or layout (which you would most certainly want to), a Version Control System (VCS) is a very wise thing to use. It allows you to revert files back to a previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more. Using a VCS also generally means that if you screw things up or lose files, you can easily recover. In addition, you get all this for very little overhead. Git can be installed [here](https://git-scm.com/downloads).

Other than installation, we don't deal with Git too much, so we can move on to the fun stuff, like MongoDB and Studio3T!


# Installing MongoDB
Mongo is an open source schemaless database system that is very different from the more popular MySQL. The most considerable differences are that MySQL is written using SQL Queries, whereas MongoDB is focused on BSON data (binary JSON). MongoDB can be downloaded [here](https://www.mongodb.com/download-center#community). When downloading, make sure to select the community server version that corresponds to your computer's operating system.

###### Notes:
###### - MongoDB for Windows 64-bit runs only on Windows Server 2008 R2, Windows 7 64-bit, and newer versions of Windows. This build takes advantage of recent enhancements to the Windows Platform and cannot operate on older versions of Windows.
###### - MongoDB for Windows 64-bit Legacy runs on Windows Vista, and Windows Server 2008 and does not include recent performance enhancements.

To find out which version of Windows you are running, enter the following commands on Command Prompt
```
wmic os get caption
wmic os get osarchitecture
```

# Installing Studio3T
To work with our MongoDB data, we will use Studio3T, an open-source MongoDB client with a built-in shell to write scripts. Studio 3T can be downloaded [here](https://studio3t.com/download/). Although that the download states that Studio3T is free for only 14 days, it is actually free forever for non-commercial use! After opening up Studio3T, you will see a message bar at the bottom with an option to select usage types, so simply select "non-commercial" and you should be all set!


# Installing OpenVPN
The last thing we need to install is OpenVPN, a tunnel that allows us to access to the MongoDB server through a secure connection. For Windows users, use [this link](https://openvpn.net/index.php/download/community-downloads.html) to install OpenVPN. If you're running iOS, the installation documentation can be found [here](https://openvpn.net/index.php/open-source/documentation/howto.html).

AFter installing OpenVPN, you'll need to contact Mike to help you get setup with a script for your connection. The script should have an ".ovpn" extension.

After you receive your connection script, copy that file into your 'config' folder within the OpenVPN folder.

### Windows Users
Your OpenVPN folder should have saved to your "C:\Program Files\" directory. In command prompt, navigate to the 'config' folder in your OpenVPN folder through using these commands:
```
cd..
cd name of folder
```
*The "cd.." command will help you backtrack exactly one directory. For example, if you're in the "C:\Program Files\" directory, the "cd.." command will take you to the "C:\" directory.* 

*The "cd name of folder" command will take you into a folder within the directory that you're in. For example, "cd Program Files" will take you to the "C:\Program Files" directory if you're in the "C:\" directory when you run the command.*

Once you've navigated to the 'config' folder within the OpenVPN folder, run the following line on command prompt
```
openvpn nameOfYourOpenVPNFile.ovpn
```
After this point, you should be connected to the server. To check, you can check the OpenVPN icon on your taskbar, or simply run this command
```
openvpn-gui --connect office.ovpn
```
If this returns a pop-up message stating that you're connected to the VPN, then voilà! If not, then the command will connect you to the VPN.

You will then be prompted to enter your username and password to establish the connection. From now on, the OpenVPN icon will show up on your taskbar at the lower right hand corner of your screen. To disconnect/connect to the VPN, simply right-click on the icon and select your preference.

### iOS Users
To connect to OpenVPN Access Server using the Connect Client you will need to navigate to the Connect Client for your particular access server. The url is usually "https://" + "yourvpnhostname.com".

After entering your credentials you will be asked to download the installer: ![installer download](http://openvpn.net/images/howto/osxconnect/mac-openvpn-connnect-3.png)

After downloading and running the installer you will be prompted to continue with the installation: ![installation](http://openvpn.net/images/howto/osxconnect/mac-openvpn-connnect-4.png)

Keep clicking continue and choose a destination to install the software to. After entering your credentials (this will be provided by Mike), you will be brought back to the browser and the client will begin running. You should see the OpenVPN GUI icon at the top right corner of your screen with a message saying that your connection has been established.

From now on, to connect/disconnect to the server, simply click on the OpenVPN icon and select "connect" or "disconnect".

# Connecting to MongoDB through Studio3T
Studio3T provides a user-friendly way to make queries, view data, and sort data. When starting Studio3T, click connect and enter the following information. Note: you must be connected to the VPN in order to be able to access the database! 

![info](https://github.com/adgoradia/newGitTest/blob/master/image.png)

After connecting, you should see the database and its collections on the left side of Studio3T. 

![view](https://github.com/adgoradia/newGitTest/blob/master/imag.png)
