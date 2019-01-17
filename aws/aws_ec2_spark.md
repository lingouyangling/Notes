# set up ec2 with jupyter notebook
## 1. launch an ubuntu instance    
## 2. config the security group   
## 3. ssh to the instance
```shell
ssh -i filename.pem ubuntu@public_dns
```
## 4. install anaconda
download
```shell
wget https://repo.continuum.io/archive/Anaconda3-2018.12-Linux-x86_64.sh
```
install
```shell
bash Anaconda3-2018.12-Linux-x86_64.sh
```
make sure anaconda is the default python
## 5. set a password for jupyter  
```shell
ipython
```
```shell
from IPython.lib import passwd
```
```shell
password()
```
follow the steps and copy paste the hashed password to somewhere
```shell
exit
```
## 6. creat a jupyter config file
```shell
jupyter notebook --generate-config
```
## 7. create certificate
```shell
mkdir certs
```
```shell
cd certs
```
```shell
sudo openssl req -x509 -nodes -days 365 -newkey rsa:1024 -keyout mycert.pem -out mycert.pem
```
answer the prompt questions   
## 8. change the ownership of the certificate
```shell
sudo chown $USER:$USER ~/certs/mycert.pem
```
## 9. config jupyter notebook
```shell
cd ~/.jupyter/
```
```shell
vi jupyter_notebook_config.py
```
insert this at the beginning of the file:
```python
c = get_config()
c.IPKernelApp.pylab = 'inline'
c.NotebookApp.certfile = u'/home/ubuntu/certs/mycert.pem'
c.NotebookApp.ip = '0.0.0.0'
c.NotebookApp.open_browser = False
c.NotebookApp.password = u'shaxxxxxxxxxxxxxxxx' # the hashed password of jupyter
c.NotebookApp.port = 8888
```
save and quit the file
## 10. start the notebook
```shell
jupyter notebook
```
open a browser and type 'https://ec2_dns_address:8888/', check if it works
# set up spark
## 1. install java
```shell
sudo apt-get install default-jre
```
check version
```shell
java --version
```
## 2. install scala
```shell
sudo apt-get install scala
```
check version
```shell
scala --version
```
## 3. install python-java hook
```shell
pip3 install py4j
```
## 4. install spark
download
```shell
wget https://archive.apache.org/dist/spark/spark-2.4.0/spark-2.4.0-bin-hadoop2.7.tgz
```
install
```shell
sudo tar -zxvf spark-2.4.0-bin-hadoop2.7.tgz
```
## 5. install findspark
```shell
conda install -c conda-forge findspark
```
# test
open a jupyter notebook
```python
import findspark

findspark.init('/home/ubuntu/spark-2.4.0-bin-hadoop2.7')

import pyspark
```
if these importing works, then pyspark will work, done!   
