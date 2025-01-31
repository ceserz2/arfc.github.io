---
layout: manual
title: Cyclus
subtitle: "Cyclus - Creating your Ubuntu Environment"
permalink: /manual/guides/cyclus
---

## Step 0. Clean Install Ubuntu
Make sure your Ubuntu environment is clean to ensure the script works. 
This is most easily done by performing a fresh install of Ubuntu. Otherwise,
check that previous installations of cyclus have been removed, and the 
bashrc file is in the default state. 

## Step 1. Get the Script
Clone the script from [here](https://github.com/arfc/scripts). Make sure you have
both the `startup.sh` and `toBash.txt` files.
```git clone git@github.com:arfc/scripts && cd scripts```
## Step 2. Run the script
Change to the directory containing the script and proceed to run it with the following:
```
cd ~/scripts/cyclus-setup && bash startup.sh
```
The script will prompt you asking what to install.

For this installation we will be primarily concerned with a conda installation, therefore we install
the following options:

| Prompt | Input |
|:-------|------:|
|Update Bashrc  |  ` 1`   |
|Install Cyclus Dependencies (apt) | `2` |
|Install Conda 3 | `1` |
|Install Cyclus Dependencies (conda) | `1` |
|Install Pyne | `1` |
|Install Jupyter Extensions | `1` (Optional) |
|Setup Git | `1` |
|Install Sublime Text | `1` (Optional) |
|Install Other Software | `2` |

** `1` and `2` correspond to the displayed Yes and No options respectively.

## Step 3. Clone Cyclus and Cycamore Repositories
The repositories are found here for [cyclus](https://github.com/cyclus/cyclus) and 
[cycamore](https://github.com/cyclus/cycamore).

Likewise, the following can be entered in the terminal:
```
cd ~ && git clone https://github.com/cyclus/cyclus && git clone https://github.com/cyclus/cycamore
```

## Step 4. Installation
With the dependencies installed, and the repositories downloaded we can proceed to build from source.
This is accomplished by running the `setup.py` scripts in each directory.

```
cd ~/cyclus && python setup.py
```

After Cyclus is installed, we proceed to Cycamore:
```
cd ~/cycamore && python setup.py
```

If both have successfully installed, we must now verify they perform as intended with unit tests:
```
cyclus_unit_tests && cycamore_unit_tests
```
