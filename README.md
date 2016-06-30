### SparkSummitDemo
--- 

This repository contains a Python Notebook and R Shiny App created using IBM Data Science Experience.  Sign up or log-in on [Data Science Experience](http://datascience.ibm.com/) and follow along with the steps below.

--- 

###### 1. Data Science Experience Set up
- First [download the repository](https://github.com/IBMDataScience/SparkSummitDemo/archive/master.zip) to your local environment (you will upload files from the data directory to Object Storage)
- Log-in to Data Science Experience and click Start a Notebook
- If you have not started any Spark services, click the link to create a Spark instance
  - You will need to connect your BlueMix at this time
  - The first part is configuring the Spark instance
  ![spark setup](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/sparkSetup.png)
  - The second step is to add a Object Store, add a container name that is easy to remember
  ![object store setup](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/objectStoreSetup.png)
- Once the service is added, go back to your Spark instance and click Manage Object Storage under Actions
  ![manage object store](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/ManageObjectStorage.png)
- There will be a card for your object store - click that to go to Bluemix to add your files
- In Bluemix you will see the container created when the Spark instance was created
- Click Actions then Add File - you need to add BlocPower_T, CDD-HDD_Features, and HDD_Features
 ![add files in object store](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/addFiles.png)
 ![files needed](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/files.png)
- Now you are ready to run a notebook using these data sources


###### 2. Running Jupyter Notebook
- Click on New Notebook
- Click the tab for From URL, add a Name for the notebook 
- Copy the URL for the Jupyter notebook - https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/BlocPower%20with%20Sparkling.ipynb
- For the Spark Service, select the service created in step 1 that has the Object Store associated with it, create the notebook
- To read the data from the right location, the container name chosen in step 1 needs to be inserted in the first three code cells
- For the code example below, my container was named notebooks (default in Data Science Experience):
  ```
    file1 = 'swift://notebooks.spark/BlocPower_T.csv'
 ```
- If you forgot your container name, click on Data Source on the right side bar and click "Insert to code" for one of the files, this will show the container name
![notebook sample code](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/Screenshots/notebook.png)
- Now you can run each cell to recreate the analysis
- Follow along each of the following steps:
  - Data cleaning
  - Fitting a linear regression model
  - Conducting k-means clustering

###### 3. Running the Shiny App - Flex Dashboard
- Open RStudio in Data Science Experience from the left navigation bar 
- Create a new R Markdown Document - note you may be required to download some R packages at this time
- Copy the raw [R Markdown from here](https://raw.githubusercontent.com/IBMDataScience/SparkSummitDemo/master/shinyDemo.Rmd)
- Replace the default content in the new R Markdown file by pasting the code in the file
- Select lines 21 - 65 and execute (This is a one time set up to install all necessary packages)
- Click the Knit button with the ball of yarn next to it
- Ignore the error on the pop-up and click the button "Open in Browser" to see the app in a web browser
- Open the app in a browser to interact with it, share the link with anyone
