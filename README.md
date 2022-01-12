# BlazeFace PyTorch Model

Create an root folder.
    
    mkdir Blaze-Face-Model
    
Go to root folder directory.
  
    cd Blaze-Face-Model
## Create Python virtual environments 

Get and install BlazeFace PyTorch Model
    
    git clone https://github.com/hollance/BlazeFace-PyTorch.git

Download python3.8 -venv to create environment:
    
    sudo apt install python3.8-venv
    
Create python environment  
    
    python3 -m venv model-env
    
Activate python environment
   
    source model-env/bin/activate

## Install essential packages that will be used by BlazeFace PyTorch Model building

Install required packages:
    
    pip install numpy
    pip install torch

Also you can install all required packages with following command.
  
    pip install -r requirements.txt

## Building Sepecialized Docker Image for TFLite Models
    
    docker build -t kyc_blazeface .
    
Run the docker container with the image kyc_blazeface
    
    docker run -it -d --name=testblazeface -v $PWD:/home/jupyter_root -v $PWD/dataset_root:/home/dataset_root -p 8888:8888 kyc_blazeface /bin/bash -c "jupyter notebook --ip=0.0.0.0 --port=8888 --notebook-dir=/home/jupyter_root --allow-root --no-browser > jup.log"

## Using the System

Running docker will create an html page that contains url with token which is essential to access jupyter web server.
Please get on the running container shell;

    docker exec -it <container id>  bash

To view the URL with token please issue following command;
          
    jupyter notebook list
          
Copy/paste the viewed URL into your browser.

