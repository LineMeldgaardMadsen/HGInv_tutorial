Example 1: 1D infiltration
=====

In this example, the hydaulic conductivity in determined in a two-layed model using a electric resistivity sounding.


.. _Problem description

Problem description
------------

A 1D hydrologcal model is defined by an upper layer of a loamy sand 

**Geophysical data**

To calibrate the hydrological model, a geophysical dataset of electric resitivity data have been measured once a day for 50 days after the begening of the infiltration. 
Each day, 20 quadropole sounding were measured using a Schulemberger electrode configureation. 
The synthetic dataset can be accesed here: 

.. _Solvoing the problem

Solvoing the problem
------------

First, we import the needed Python packages:

.. code-block:: console
  import os
  import sys
  import numpy as np
  import pandas as pd
  import math
  import matplotlib.pyplot as plt
  import phydrus as ps
  
We define the working directory

.. code-block:: console
    # Define working directory
    wd = (r"p:\...\Ex1") 
    print("Working directory:           ",wd)

    # Working directory and path to HYDRUS.exe
    hydrus_wd = os.path.join(wd,"HYDRUS\WorkingDirTEM") # This folder will be created by hydrus 
    hydrus_exefile = os.path.join(wd,"HYDRUS\hydrus.exe")
    print("Working directory HYDRUS:    ", hydrus_wd)
    print("HYDRUS exe file:             ", hydrus_exefile)

    # Files used to compute the ERT forward response
    AarhusInv_wd = os.path.join(wd,"AarhusInvTEM") #This folder must contain the folloing files:
    AarhusInv_exefile = os.path.join(AarhusInv_wd,"AarhusInv64_v10.1.exe")
    print("Working directory AarhusInv: ", AarhusInv_wd)
    print("AarhusInv exe file:          ", AarhusInv_exefile)
    confile = os.path.join(AarhusInv_wd,"DefaultConfile.con")
    

**The hydrological model**

Here, the hydrological model described above is initialized in term for infiltration and assumed electrical properties. 

.. code-block:: console
  # Initialize hydrological parameters
  infil = 0.03          # Infiltration, m/day, constant for 50 days
  con_infil = 200       # Electric water conductivity of infiltration, mS/m 
  con_init = 50         # Initial water conductivity, mS/m
  Ndays = 50            # Days of infiltration 
  Nsteps = 10           # Number of observation steps
  Nlayers = 20          # Number of layeres in the geophysical model

  # Electrical properties and initial condistions:
  F_1 = 4.0             # Formation factor
  con_surf_1 = 2.0      # Surface conductiviyt, mS/m
  head_init_1 = -0.4629 # Initial pressure head, m
  wc_init_1 = 0.0946    # Initial moist/water content
  F_2 = 6.0             # Formation factor
  con_surf_2 = 7.0      # Surface conductivitu, mS/m
  head_init_2 = -2.105  #Initial pressure head, m
  wc_init_2 = 0.2725    #Initial moist/water content

.. code-block:: console
