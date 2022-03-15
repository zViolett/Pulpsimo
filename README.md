# Tutorial
### Install Tool-chain
## Get tool-chain
```Shell
sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev

git clone --recursive https://github.com/pulp-platform/pulp-riscv-gnu-toolchainhell

```
## Install pulp toolc-chain
```Shell
cd pulp-riscv-gnu-toolchain

./configure --prefix=/opt/riscv --with-arch=rv32imc --with-cmodel=medlow --enable-multilib

make
```
-You'll need to give permissionn for /opt folder or just use "sudo make" if you meet this error
```Shell
mkdir -p -- /opt/riscv /opt/riscv
mkdir: cannot create directory ‘/opt/riscv’: Permission denied
mkdir: cannot create directory ‘/opt/riscv’: Permission denied
```
