[![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg?style=flat)](https://github.com/emcrisostomo/docker-machine-create-rancher-vm/blob/master/LICENSE)

docker-machine-create-rancher-vm
================================

`docker-machine-create-rancher-vm` is a shell script that helps the user create
RancherOS virtual machine using `docker-machine`.  The currently supported
`docker-machine` drivers are:

  * `hyperv`
  * `virtualbox`
  * `vmwarefusion`
  * `vmwarevsphere`

Prerequisites
-------------

`docker-machine-create-rancher-vm` requires the following programs to be present
on the `${PATH}`:

  * `curl`
  * `docker-machine`
  * `zsh`

Getting docker-machine-create-rancher-vm
----------------------------------------

A user who whishes to build this package should get a [release
tarball][release].  A release tarball contains everything a user needs to build
the package on his system, following the instructions detailed in the
Installation section below and the `INSTALL` file.

A developer who wishes to modify this package should get the sources (either
from a source tarball or cloning the repository) and have the GNU Build System
installed on his machine.  Please read `README.gnu-build-system` to get further
details about how to bootstrap this package from sources on your machine.

Getting a copy of the source repository is not recommended unless you are a
developer, you have the GNU Build System installed on your machine, and you know
how to bootstrap it on the sources.

[release]: https://github.com/emcrisostomo/docker-machine-create-rancher-vm/releases

Installation
------------

See the `INSTALL` file for detailed information about how to configure and
install this package.

Usage
-----

The syntax is the following:

    Usage:
    ${PROGNAME} (options)*
    ${PROGNAME} -h
    ${PROGNAME} -v

    Options:
     -c, --cpu-count  Set the number of CPU cores.
     -d, --disk-size  Set the size of the root disk (in MB).
         --driver     Set the docker-machine driver.
     -h, --help       Print this message.
     -n, --name       Set the name of the virtual machine.
     -r, --ram-size   Set the amount of RAM allocated to the virtual machine.
     -v, --verbose    Print verbose output.
         --version    Print the program version.

The script may be invoked without any argument, in which case a virtual machine
with the following characteristics will be created:

  * CPU count: 1
  * Disk size: 8 GB
  * Driver: `vmwarefusion`
  * Name: `rancheros-vm`
  * RAM: 4096 MB

Configuration parameters can be overridden by either:

  * Setting the following environment variables:
    - `VM_CPU_COUNT`
    - `VM_DISK_SIZE`
    - `VM_DRIVER`
    - `VM_NAME`
    - `VM_RAM_SIZE`

  * Using the command line options described in the command synopsis.

Command line options take precedence over environment variables.

Bug Reports
-----------

Bug reports can be sent directly to the authors.

-----

Copyright (c) 2020 Enrico M. Crisostomo

This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation; either version 3, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program.  If not, see <http://www.gnu.org/licenses/>.
