## Updating the package information
```bash
sudo apt-get update
```
## Installing the dependencies

```bash
sudo apt-get install \
m4 tcsh csh libx11-dev libx11-xcb-dev tcl-dev tcllib swig \
tk-dev libcairo2-dev mesa-common-dev xterm libglu1-mesa-dev \
libncurses-dev build-essential clang bison flex intltool \
libreadline-dev gawk libffi-dev git libgtk-3-dev graphviz \
xdot pkg-config python3 libboost-system-dev vim-gtk3 \
adms autoconf automake libtool libxpm-dev libxaw7-dev \
libssl-dev libboost-python-dev libboost-filesystem-dev \
zlib1g-dev checkinstall --assume-yes
```
## Installing the CMAKE
```bash
sudo snap install cmake --classic
```
## Installing modified GAW 
```bash
git clone https://github.com/StefanSchippers/xschem-gaw
cd xschem-gaw
aclocal && automake --add-missing && autoconf
sed -i 's/GETTEXT_MACRO_VERSION = 0.18/GETTEXT_MACRO_VERSION = 0.20/' ./po/Makefile.in.in
./configure
make
sudo checkinstall --default --pkgname=xschem-gaw --pkgversion=0.1
cd
```
## while simulating in xschem NGSPICE use follwing in cmd prompt of NGSPICE
```
write <file_name>.raw
```

## the file will be saved in .xschem folder in HOME dir 
## use ctrl+h to show hidden files
## in GAW open file - file location - open .raw file
