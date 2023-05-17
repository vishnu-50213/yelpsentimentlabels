# yelpsentimentlabels  
Project Name: Using Big Data Techniques for Analysis Yelp Data and Generate Useful Insights

Table of contents: 
	Introduction
	Software Requirements
	Recommended Hardware
	Installation
	Configuration
	Execution
	FAQ

Introduction: 
	This project aims to use massive amount of data of the order  10Gb in magnitude and over 70 million rows of yelp data.
	For generation of insights and a prediction model using Text model algorithms.
	This "readme.txt" file aims to help the users with the required installations, configuring the environment and setup required to run the code.


Software Requirements:
	Python version 3.11
        Colab environment 
	PySpark version 3.3.2 and spark jars should be same version
	Windows version 10/11 or  Mac



Recommended Hardware Specifications:
	32Gb or higher RAM - 3000Mhz or Higher frequency recommended.
	or else Colab pro is option.
        If everything is not possible, go with as high RAM as possible.


For local Installation:
	Python installation:
		1. From www.python.org, select the version of python 3.11, select windows 64 bits or Mac.
		2. Run the installer, tick both check boxes (installation, adding path).
		3. click "install now".
		4. Once installation is complete, close the installer.
		5. To verify the installation process, open CMD and run the command "python". This will display the current version of python. Do the same thing in Mac in terminal.
		7. Installation and setup of Python is complete. 
	
	Jupyter Installation:
		1. in CMD, run the command, "pip install notebook" for installing Jupyter.
		2. To run the notebook use "Jupyter notebook".
                3. For Mac, install first home-brew then everything we can install using home-brew.
	
	AWS Installation:
		1. Sign up in AWS console, then create bucket in s3.
		2. In that we can drag and drop every file we are gonna use, it require high ethernet speeds while drag and drop feature.
		3. If you got slow ethernet, we can access s3 from python notebook, we can use multipart rope to upload large files. Small value file can easily done in drag and drop. For this we need boto3 library in python file
		4. Then we can go with creating user from IAM option in AWS.
		5. Grant programatic access to created user.
		6. Download the credentials of that user.
		7. If we got credentials then we can go with python notebook. And boto3 is also require credentials while uploading.
		
		
	PySpark for Windows Installation:
		1. Open "https://spark.apache.org/downloads.html" with the browser.
		2. Choose a Spark release: 3.3.2   we faced AWS access error while using latest versions and we checked lot of versions. We got this version better
		   Choose a package type: Pre-built for Apache Hadoop 3.3 and later
		   Download Spark: spark-3.3.2-bin-hadoop3.tgz
		3. extract the binary using 7zip and copy the underlying folder spark-3.0.0-bin-hadoop2.7 to c:\apps
		4. Now set the following environment variables.
		   SPARK_HOME  = C:\apps\spark-3.3.2-bin-hadoop2.7
		   HADOOP_HOME = C:\apps\spark-3.3.2-bin-hadoop2.7
           PATH=%PATH%;C:\apps\spark-3.3.2-bin-hadoop2.7\bin
		5. Download winutils.exe file from win utils, copy it to %SPARK_HOME%\bin folder.
		6. Open the command prompt and type pyspark command to run the PySpark shell. 
		
Configuration:
		Setting-1 :
		Add the following configuration to the PySpark session:
		spark.driver.memory 15gb 
		using same spark jars version of hadoop-aws and common we can access data dynamically from AWS s3.

Execution:

	Fetching data : 
		The data is downloaded from the source -> https://www.yelp.com/dataset/download
		The total size of the data is : around 10 GB.
		The total number of JSON files are: 5 Files.

		
		
	Running the primary code:
	Run the notebook using the Colab ( best option ). We don't need to face checking different versions or mismatch problems.
		Phase-1 : This step does the cleaning of data. 
		Phase-2 : This step does the understanding of data	
		Phase-3 : topic modeling, we done tokens then removing of stop word. After getting resulted data we vectorized it then feed the data to LDA model.
                Phase-4: Sentiment analysis on the same vectorized data. 
		
		
FAQ: 
	1. What if you are encountering a memory allocation error using PySpark ?
	This issue is fixed using the configuration presented  above, that ensures that PySpark always has access to a minimum amount of memory.
	
Additional Resources:
https://sparkbyexamples.com/
https://www.tutorialspoint.com/how-to-install-python-in-windows






