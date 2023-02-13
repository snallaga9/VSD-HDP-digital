### TOOL CHECK
1.   yosys
1.   OpenSTA
1.   ngspice
1.   iverilog
1.   gtkwave
1.   magic


## yosys: 
### installation: 
$ git clone https://github.com/YosysHQ/yosys.git
//here I had created yosys directory in which github repo is cloned
![pg-1](https://user-images.githubusercontent.com/110479456/218370301-4cef7218-eb3a-4345-8f0a-7418a3155380.png)

$ cd yosys
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
![pg-2](https://user-images.githubusercontent.com/110479456/218370765-b1a00d43-2b2f-4b47-b226-0ad60fee523c.png)
$ make 
$ sudo make install

Useful link: [yosys](https://yosyshq.readthedocs.io/projects/sby/en/latest/install.html#yosys-yosys-smtbmc-and-abc)

