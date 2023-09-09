# Docker intallation

## Instsll Docker 

You can install Docker following instrution here [link](https://docs.docker.com/engine/install/).

## Run container

#### Pull image

~~~~
docker pull likask/mofem-spack-jupyterhub:Workshop2023
~~~~

#### Run container

If you like just try, after shutdown of the JupyterHub container will be romoved run docker it as follows, 
~~~~
docker run --rm --name workshop2023 -p 8000:8000 -p 2222:22 likask/mofem-spack-jupyterhub:Workshop2023
~~~~

#### Run deomon 

If you like to switch it on for some time, we recommend to run it as a deaom,
~~~~~
docker run -d --name workshop2023 -p 8000:8000 -p 2222:22 likask/mofem-spack-jupyterhub:Workshop2023
~~~~~
In case you run it on the laptop, and you shout it down, you adter reboot you can restart container as follows
~~~~~
docker start workshop2023
~~~~~

#### M1 chip case on Mac

If you have run Mac with ARM chip, you have to switch platofrm when you run compiler,
~~~~~~
docker run -d --platform linux/amd64 --name workshop2023 -p 8000:8000 -p 2222:22 likask/mofem-spack-jupyterhub:Workshop2023
~~~~~~
that rensers suboptimal prefromance, however is a workable solution.

In theroy, you can build your docer image from M1 chip, however, we do not test it and at and that time we do not know if all packages will run. However, MoFEM compilation with Spack will work. 

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
You can use other shells, depending of your personal preferences.

### SSH config

Copy the following code into .ssh/config on your laptop or desktop.
~~~~
Host workshop2023
  HostName localhost
  ForwardX11 yes
  Compression yes
  User YOUR_LOGIN_ON_HUB
  Port 2222
~~~~

Use *workshop2023* when you login in VSCode. Note tha you are connecting to *jupyterhub cloud/docker container*.

### Video on JuputerHub, SSH and MoFEM

[![Watch the video](https://img.youtube.com/vi/xL3J8VHig68/hqdefault.jpg)](https://youtu.be/xL3J8VHig68){:target="_blank" rel="noopener"}

