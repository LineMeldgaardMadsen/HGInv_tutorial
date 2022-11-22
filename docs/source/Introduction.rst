Introduction
=====

In this tutorial, you will be guided through a selection of Python notebooks that can be used for coupled hydrogeophysical inversion. The aim of the hydrogeophysical inversion is to calibrate the hydraulic conductivity of a hydrological model using geophysical data.

.. _installation:

Installation
------------

Before runneing the notebooks, a series of Python Libaries and geophysical/hydrological modelling softwares must be installed.
The instalations needed depends on the geophysical modalites and the hydrological software you want to use.

Hydrological modelling

To call HYDRUS-1D from the notebooks, we use the wrapper PHYDRUS. This is installed and hereafter importet with the following:

.. code-block:: console

   !{sys.executable} -m pip install phydrus
   import phydrus as ps

Geophysical modelling

To compute the geophysical foorward responses, we use exsisting modelling software. 

For 1D/2D/3D electric resistivity and TEM, we use AarhusInv, which work by writing/reading input/output to/from an exe-file (AarhusInv.exe), which can be downloaded at hgg.au.dk.

For FEM forward modelling, we use EMagPy, which is a Python package that can be installed and imported with the following:

.. code-block:: console

   !{sys.executable} -m pip install emagpy
   from emagpy import Problem

.. _Synthetic geophysical data:

Synthetic geophysical data
------------
