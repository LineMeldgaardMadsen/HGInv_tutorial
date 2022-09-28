Tutorial on coupled hydrogeophysical inversion 
===================================

In this tutorial, you will be guided through a selection of Python notebooks 
that can be used for coupled hydrogeophysical inversion. The aim of the hydrogeophysical 
inversion is to calibrate the hydraulic conductivity of a hydrological model using 
geophysical data.

The notebooks combines different geophysical and hydrological modelling softwares in 
an Monte Carlo Markov Chain optimization to calibrate the hydraulic conductivity of 
the hydrological model. The Notebooks are put togeather in a flexible way allowing the 
used of different geophysical data type and different hydrological modeles, so the framework 
can be adapted to any hydrolgeophysical problem.

The following geophysical data types are implemented:
   - 1D electric resistivity (using AarhusInv)
   - 2D electric resistivity (using ResiPy)
   - 1D time-domain electrocmagnetics (using AarhusInv)
   - 1D frequency-domain electrocmagnetics (using AarhusInv or MagPy)

Examples exsists using the following hydrological modelling softwares
   - HYDRUS-1D
   - SUTRA
   - MODFLOW-SEAWAT


Contents
--------

.. toctree::

   Introduction
   Theory
   Example1
