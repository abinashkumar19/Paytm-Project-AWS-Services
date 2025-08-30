#-----------------------------  commands to install mysql  ------------------------------

sudo yum update -y

sudo dnf install -y mariadb105


#----------------------------   commands to install python 3   -----------------------------------------------

# Update system
sudo yum update -y

# Install Python 3 and pip
sudo yum install python3 -y

# Ensure pip is installed
sudo yum install python3-pip -y

# Verify installation
python3 --version
pip3 --version

# Install Flask
pip3 install Flask

# Install MySQL connector
pip3 install mysql-connector-python

#install flask core 
pip3 install flask-cors
