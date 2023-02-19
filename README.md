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


##  OpenSTA
### installation:
$ git clone https://github.com/The-OpenROAD-Project/OpenSTA.git
![pg-3](https://user-images.githubusercontent.com/110479456/218372713-6b00229a-625b-4881-8248-6005fbd92e1a.png)

$ cd OpenSTA

$ mkdir build

$ cd build

$ cmake .. 

$ make

![pg-4](https://user-images.githubusercontent.com/110479456/218374497-c939c539-95ec-4824-b9ae-6caf896eb399.png)


##  ngspice
### installation: 
$ sudo apt-get install ngspice
![pg-5](https://user-images.githubusercontent.com/110479456/218374915-0951760f-f909-4112-bf55-e6b00460532b.png)


##  iverilog
### installation:
$ sudo apt-get install iverilog
![pg-6](https://user-images.githubusercontent.com/110479456/218374944-5399414d-bab0-4734-9166-1237d1030627.png)


##  gtkwave
### installation:
$ sudo apt-get install gtkwave

##  magic
### installation:
$   sudo apt-get install m4

$   sudo apt-get install tcsh

$   sudo apt-get install csh

$   sudo apt-get install libx11-dev

$   sudo apt-get install tcl-dev tk-dev

$   sudo apt-get install libcairo2-dev

$   sudo apt-get install mesa-common-dev libglu1-mesa-dev

$   sudo apt-get install libncurses-dev
![pg-7](https://user-images.githubusercontent.com/110479456/218375598-2665721d-ad5b-485c-a605-3733368646a8.png)



## Simulator
### executing steps:
* **iverilog design_file.v testbench_design_file.v** 

// you can also give iverilog design_file.v testbench_design_file.v -o design_executable

* **./a.out** 

//this a.out executable file is generated or ./design_executable if you have specified any

* **testbench_design_file.vcd** 

//vcd dump file is generated

* **gtkwave testbench_design_file.vcd** 

//waveform viewer will openup with the input & output stimulus.


## synthesis
### executing steps:
1. **read_liberty -lib $PATH/*.lib** 

// in our case read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

* you are reading the .lib content //all the models

2. **read_verilog design.v**

//reading the design or loading the design

3. **synth -top design_name**

//give design_name for it to be relevant

* read the statistics it prints to see the models it loads for the design.

4. **abc -liberty $PATH/*.lib**

//technology mapping using ABC

5. **show design_name**

//design_name given in the synthesis run step.3 "synth -top design_name"

6. **write_verilog -noattr design_name_netlist.v**

//writing out the synthesized netlist with technology mapped logic gates

## GLS [Gate Level Simulation]
link: https://github.com/snallaga9/VSD-HDP-digital/wiki/WEEK-1#day-4--gls-gate-level-simulation
