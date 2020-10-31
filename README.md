# yelp_sentiment


Google Cloud Platform for Machine Learning

Follow the steps below:
### 1. Create VM instance
Configure based on the computational needs.

### 2. Setup for SSH access
RSA Key

### 3. Create firewall rules (to allow jupyter notebook port, usually 80)

### 4. Install Anaconda / Jupyter Notebook

#install Anaconda<br>
" wget https://repo.continuum.io/archive/Anaconda3-5.3.1-Linux-x86_64.sh <br>
" bash Anaconda3-5.3.1-Linux-x86_64.sh

#install Jupyter Notebook<br>
"conda install notebook

### 5. Configure Jupyter Notebook setting

jupyter notebook --generate-config 
nano ~/.jupyter/jupyter_notebook_config.py

Insert as below <br>
c = get_config()<br>
c.NotebookApp.ip = '*'<br>
c.NotebookApp.open_browser = False<br>
c.NotebookApp.port = 80<br>

### 6. Use browser to open jupyter notebook

jupyter-notebook --no-browser --port=80

[external IP address]:[port number] in your browser



## Use Kaggle API to Download Data Directly to Cloud Instance

### 1. Install Kaggle: SSH into your instance, and pip install kaggle <br>
### 2. Get API Credentials All API requests need credentials to identify yourself. Just go to https://www.kaggle.com/[kaggle_username]/account, scroll down and click “Create API Token”. It will download kaggle.json with your username & authkey.<br>
### 3. Load Credentials on Instance You need to put kaggle.json into /home/[user name]/.kaggle.<br>
### 4. Download your dataset You can just use this command:<br>
kaggle datasets download -d [dataset_identifier] -p *your_destination_path*

To get dataset_identifier, you can just browse to the dataset you want on the kaggle website. 
There’s actually a button that helpfully gives you the API command directly.


In case you want to unzip file on ssh follow the command below.<br>
$ sudo apt install unzip<br>
$ unzip [file name]<br>



