---
tags: tc, tiger, tiger compiler, compiler, libraries
author: Robin Boucher
date: 02/28/19
---

# Every library needed for compiling the Tiger Compiler project

## Installation of custom bison/havm/monoburg/nolimips
Copy the following code in a file:
```
#!/bin/sh

# Install HAVM
wget https://www.lrde.epita.fr/~tiger/download/havm-0.27.tar.gz
tar -xzvf havm-0.27.tar.gz
cd havm-0.27
./configure
make
make install
cd ..
rm  havm-0.27.tar.gz

# Install Monoburg
wget https://www.lrde.epita.fr/~tiger/download/monoburg-1.0.6a.tar.gz
tar -xzvf monoburg-1.0.6a.tar.gz
cd monoburg-1.0.6a
./bootstrap
./configure
make
make install
cd ..
rm monoburg-1.0.6a.tar.gz

# Install Nolimips
wget https://www.lrde.epita.fr/~tiger/download/nolimips-0.10.tar.gz
tar -xzvf nolimips-0.10.tar.gz
cd nolimips-0.10
./bootstrap
./configure
make

# Dirty quick fix
cp src/nolimips /usr/local/bin
mkdir /usr/local/bin/.libs
cp src/.libs/nolimips /usr/local/bin/.libs

cd ..
rm nolimips-0.10.tar.gz

# Install custom Bison
wget https://www.lrde.epita.fr/~tiger/download/bison-3.2.1.52-cd4f7.tar.gz
tar -xvf bison-3.2.1.52-cd4f7.tar.gz
cd bison-3.2.1.52-cd4f7
./configure
make
make install
cd ..
rm bison-3.2.1.52-cd4f7.tar.gz
```
Chmod it to make it executable and launch it with sudo to install the different packages:
```
chmod 700 file.sh
sudo ./file.sh
```

## Installing automake/autoconf:
`sudo apt-get install automake`
`sudo apt-get install autoconf`

## Installing libtoolize:
`sudo apt-get install libtool`

## Installing libboost:
Check this **[link](https://stackoverflow.com/a/24086375)** and adapt to version you want. If you can, take the latest stable one.

## Installing the good version of g++ and gcc
Check this **[link](https://gist.github.com/jlblancoc/99521194aba975286c80f93e47966dc5)** and adapt to the version you want. If you can, take the latest stable one.
Be aware of not messing up with symbolic links.
