# Tutorial
## Install Tool-chain
### Get tool-chain
```Shell
sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev

git clone --recursive https://github.com/pulp-platform/pulp-riscv-gnu-toolchainhell

```
### Prerequirment packages
```Shell
sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev
```

### Install pulp toolc-chain
```Shell
cd pulp-riscv-gnu-toolchain

./configure --prefix=/opt/riscv --with-arch=rv32imc --with-cmodel=medlow --enable-multilib

make
```
- You'll need to give permission for /opt folder or just use "sudo make" if you meet this error
```Shell
mkdir -p -- /opt/riscv /opt/riscv
mkdir: cannot create directory ‘/opt/riscv’: Permission denied
mkdir: cannot create directory ‘/opt/riscv’: Permission denied
```
### Add environment path and evn variable
```Shell
export PATH=/opt/riscv:$PATH
export PULP_RISCV_GCC_TOOLCHAIN=/opt/riscv
```

## Install SDK
### Install packages
```Shell
sudo apt install git python3-pip python-pip gawk texinfo libgmp-dev libmpfr-dev libmpc-dev swig3.0 libjpeg-dev lsb-core doxygen python3-sphinx sox graphicsmagick-libmagick-dev-compat libsdl2-dev libswitch-perl libftdi1-dev cmake scons libsndfile1-dev

sudo pip3 install artifactory twisted prettytable sqlalchemy pyelftools openpyxl xlsxwriter pyyaml numpy configparser pyvcd

sudo pip2 install configparser
```
### Add env variable
```Shell
export VSIM_PATH=$HOME/pulpissimo/sim
```
### Build SDK
```Shell
make build-pulp-sdk
```
### Update IP
```Shell
make checkout
```
## Run test
- First, export some system environment variables:
```Shell
source ./pulp-runtime/configs/pulpissimo.sh

source ./env/pulpissimo.sh

source ./pulp-sdk/configs/pulpissimo.sh
```
- Then, rebuild SDK:
```Shell
cd pulp-sdk
make all
```
- Configure environment for PULPsimo
```Shell
cd pulp-runtime
source configs/pulpissimo.sh
```
- Building the RTL simulation platform
```Shell
source setup/vsim.sh
make build
```
- You need a simulation tool like Modelsim/Questasim or you'll meet this error:
```Shell
/bin/bash: vlib: command not found
```
