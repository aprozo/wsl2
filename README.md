
## WSL2 Install
open Windows PowerShell (right click - "Run as administrator")

`wsl --install`  - it will install latest wsl2 Ubuntu version.

If there are any problems, one can download it from Microsoft Store : https://www.microsoft.com/store/productId/9PDXGNCFSCZV?ocid=pdpshare

I would also advice to install [Windows Terminal Preview](https://www.microsoft.com/store/productId/9N8G5RFZ9XK3?ocid=pdpshare)

Then reboot your laptop.


start new UBUNTU terminal, and update some packages (just copy/paste inside the new terminal):

``` bash
cd ~
sudo apt-get install dpkg-dev cmake g++ gcc binutils libx11-dev libxpm-dev \
libxft-dev libxext-dev python3 libssl-dev \ 
gfortran libpcre3-dev \
xlibmesa-glu-dev libglew-dev libftgl-dev \
libmysqlclient-dev libfftw3-dev libcfitsio-dev \
graphviz-dev libavahi-compat-libdnssd-dev \
libldap2-dev python3-dev libxml2-dev libkrb5-dev \
libgsl0-dev qtwebengine5-dev -y 

 cd ~
 mkdir install 
 cd install 
 wget https://root.cern/download/root_v6.28.06.Linux-ubuntu22-x86_64-gcc11.4.tar.gz
 tar -xzvf 	root_v6.28.06.Linux-ubuntu22-x86_64-gcc11.4.tar.gz 
 rm  root_v6.28.06.Linux-ubuntu22-x86_64-gcc11.4.tar.gz 
 source ~/install/root/bin/thisroot.sh
 
 sudo apt-get install firefox xdg-utils sshfs -y 
 sudo apt-get install texlive-full -y
 sudo apt-get install python3-pip
 pip install notebook
 export PATH="$HOME/.local/bin:$PATH"
```

I would also recommend to update your $HOME/.bashrc file in your Home directory, one could take an example in this repository.

At least add there :

` source ~/install/root/bin/thisroot.sh`


## Python
Miniconda install here :
https://educe-ubc.github.io/conda.html


``` bash
conda activate
conda config --set channel_priority strict
conda create -c conda-forge --name tf root
conda activate tf
pip install --upgrade pip
python3 -m pip install tensorflow==2.12
conda install -c conda-forge cudatoolkit=11.2.2
pip install cudnn==8.9.4
conda update --force conda

conda install -c anaconda pandas
conda install -c conda-forge uproot
pip install --user root_numpy
pip install --upgrade matplotlib
#pip3 install energyflow
```

Or better install from atttached environmental list 
```bash 
conda create --name tf --file condaEnv.list
````

Verify tensorflow installation :

```bash 
# Verify the installation:
python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
````





## Install on Windows

Visual Studio Code https://code.visualstudio.com/download

for SDCC :  NoMachine https://www.nomachine.com/


### VS code extensions (inside WSL2):
``` bash
code --install-extension albertopdrf.root-file-viewer 
code --install-extension eamodio.gitlens
code --install-extension esbenp.prettier-vscode
code --install-extension GitHub.copilot
code --install-extension James-Yu.latex-workshop
code --install-extension ms-azuretools.vscode-docker
code --install-extension MS-CEINTL.vscode-language-pack-ru
code --install-extension ms-vscode.cmake-tools
code --install-extension ms-vscode.cpptools
code --install-extension ms-vscode.cpptools-extension-pack
code --install-extension ms-vscode.cpptools-themes
code --install-extension twxs.cmake
```

