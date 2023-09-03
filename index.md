# Workshop 2023

![WorkshopLogo2023](figures/WorkshopLogo2023.png)

[Glasgow Computational Engineering Centre](https://www.gla.ac.uk/research/az/gcec/) of the University of Glasgow  is proud to organise the first Autumn School of the [UK Association for Computational Mechanics](https://ukacm.org).

The objective of this online course is to present new advances in mixed finite element formulations in solid mechanics and novel techniques for modelling deformable solids at finite strains. The lectures are focused on both the mechanical and mathematical aspects.  The specific topics of this course include saddle point formulations to handle incompressibility constraints, block-solvers, thermo-elasticity, novel multifield formulations for plasticity and incompressible hyperelasticity, and the recent development on the first-order hyperbolic framework for fast-transient solid dynamics. Moreover, we will also provide hands-on training with MoFEM on the cloud platform on these topics.

### Programme

Link to programme [link](https://drive.google.com/file/d/17aD4O-mxYrhhLBaUtaC6G61ZZh1P1Dwy/view)

### Being good citizen

- If you run somthing with multiprocesses and which will run longer than 5-10 minutes, be nice, i.e. run command as follows
~~~~
nice -n 10 mpirun -np 2 ./command_line
~~~~

### Password and login

- On the first login, select the password
- The shell password on the SSH login is different than the JupyterHub password
- Ask admin for SSH password
- Change password in the shell using [passwd](https://man7.org/linux/man-pages/man1/passwd.1.html){:target="_blank" rel="noopener"} command
- Set up your shell with the command (e.g. bash):
~~~~
$ usermod --shell /bin/bash your_login_name
~~~~

### SSH config if you have account on cactus

Copy the following code into .ssh/config on your laptop or desktop.
~~~~
Host workshop2023
  HostName localhost
  ForwardX11 yes
  Compression yes
  User YOUR_LOGIN_ON_HUB
  Port 2222
~~~~

Use *workshop2023* when you login in VSCode. Note tha you are connecting to *cactus* from which is tunnel to *geenstick*.

### Video on JuputerHub, SSH and MoFEM

[![Watch the video](https://img.youtube.com/vi/xL3J8VHig68/hqdefault.jpg)](https://youtu.be/xL3J8VHig68){:target="_blank" rel="noopener"}

