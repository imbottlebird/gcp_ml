# Google Cloud Platform for Machine Learning

Follow the steps below:
### 1. Create VM instance
Configure based on the computational needs.

### 2. Setup for SSH access
Generate the RSA Key and save it on the GCP platform for the authentication.

### 3. Create firewall rules<br>
This project will use port 8880.
Also, check boxes for 'allow HTTP traffic' and 'allow HTTPS traffic'.

### 4. Install Anaconda / Jupyter Notebook

install Anaconda<br>
```
wget https://repo.continuum.io/archive/Anaconda3-5.3.1-Linux-x86_64.sh <br>
```
```
bash Anaconda3-5.3.1-Linux-x86_64.sh
```
Do you wish the installer to prepend the 
Anaconda3 install location to PATH 
in your /home/haroldsoh/.bashrc ? 
[no] >>> yes

To make use of Anaconda right away, source your bashrc:<br>
```
source ~/.bashrc
```

#in case the jupyter notebook is not automatically installed, use the command line below to install.<br>
```
conda install notebook
```

### 5. Configure Jupyter Notebook setting

```
jupyter notebook --generate-config
```
```
nano ~/.jupyter/jupyter_notebook_config.py
```

Insert as below <br>
c = get_config()<br>
c.NotebookApp.ip = '*'<br>
c.NotebookApp.open_browser = False<br>
c.NotebookApp.port = 8880<br>
c.NotebookApp.token = '' #include this in case you want to disable the token authentication<br>

### 6. Use browser to open jupyter notebook

Start the jupyter notebook server<br>
```
jupyter-notebook --no-browser --port=8880
```

To access the notebook, enter "[external IP address]:[port number]" in your browser.
<br>


## Use Kaggle API to Download Data Directly to Cloud Instance

### 1. Install Kaggle<br>
```
pip install kaggle
```

### 2. Get API Credentials<br>
All API requests need credentials to identify yourself. <br>
Go to https://www.kaggle.com/[kaggle_username]/account and click “Create API Token”.
It will download kaggle.json with your username & authkey.<br>
### 3. Load Credentials on Instance<br>
You need to save kaggle.json at /home/[user name]/.kaggle.<br>
### 4. Download your dataset<br>
You can just use this command:<br>
```
kaggle datasets download -d [dataset_identifier] -p *your_destination_path*
```

For this project,<br>
```
kaggle datasets download -d yelp-dataset/yelp-dataset
```

To get dataset_identifier, you can just browse to the dataset you want on the kaggle website. 
There is a button that gives you the API command directly.


In case you want to unzip file on ssh follow the command below.<br>
```
sudo apt install unzip
```
```
unzip [file name]
```



