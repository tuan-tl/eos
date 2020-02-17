
# EOSIO Setup Guideline
This is a step-by-step guideline to install EOSIO, which can be done via 2 methods:
* [Install by Prebuilt Binaries](#Install-by-Prebuilt-Binaries)
* [Install by building from Source Code](#Install-by-building-from-Source-Code)

## Install by Prebuilt Binaries
#### Mac OS X Brew Install
```sh
$ brew tap eosio/eosio
$ brew install eosio
```
#### Mac OS X Brew Uninstall
```sh
$ brew remove eosio
```
#### Ubuntu 18.04 Package Install
```sh
$ wget https://github.com/eosio/eos/releases/download/v1.8.12/eosio_1.8.12-1-ubuntu-18.04_amd64.deb
$ sudo apt install ./eosio_1.8.12-1-ubuntu-18.04_amd64.deb
```
#### Ubuntu 16.04 Package Install
```sh
$ wget https://github.com/eosio/eos/releases/download/v1.8.12/eosio_1.8.12-1-ubuntu-16.04_amd64.deb
$ sudo apt install ./eosio_1.8.12-1-ubuntu-16.04_amd64.deb
```
#### Ubuntu Package Uninstall
```sh
$ sudo apt remove eosio
```
#### Centos RPM Package Install
```sh
$ wget https://github.com/eosio/eos/releases/download/v1.8.12/eosio-1.8.12-1.el7.x86_64.rpm
$ sudo yum install ./eosio-1.8.12-1.el7.x86_64.rpm
```
#### Centos RPM Package Uninstall
```sh
$ sudo yum remove eosio
```

## Install by building from Source Code
If you have previously installed EOSIO using build scripts, please execute `eosio_uninstall.sh` to uninstall first.

Clone EOSIO source code and update submodules:
```sh
git clone https://github.com/tuan-tl/eosio.git eosio-1.8.12
cd eosio-1.8.12
git checkout tags/v1.8.12
git submodule update --init --recursive
```
Build EOSIO binaries:
```sh
./scripts/eosio_build.sh -P
```
Install EOSIO binaries:
```sh
sudo ./scripts/eosio_install.sh
```
Update `profile` to include EOSIO path:
```sh
nano ~/.profile
PATH=$PATH:$PATH_TO_EOSIO
## for example:
## PATH=$PATH:/Users/tuantran/eosio/1.8/bin/
source ~/.profile
```
## References
* _Install Prebuilt Binaries_, EOS Developers, viewed 17 Feb 2020, <<https://developers.eos.io/manuals/eos/latest/install/install-prebuilt-binaries>>.
* _Build EOSIO from Source_, EOS Developers, viewed 17 Feb 2020, <<https://developers.eos.io/manuals/eos/latest/install/build-from-source/index>>.
* _Aliasing EOSIO components_, EOS Developers, viewed 17 Feb 2020, <<https://eosio-cpp.readme.io/v1.1.0/docs/aliasing-eosio-components>>.
