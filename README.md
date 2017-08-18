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
