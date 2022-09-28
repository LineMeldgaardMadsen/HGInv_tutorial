Introduction
=====

In this tutorial, you will be guided through a selection of Python notebooks that can be used for coupled hydrogeophysical inversion. The aim of the hydrogeophysical inversion is to calibrate the hydraulic conductivity of a hydrological model using geophysical data.

.. _installation:

Installation
------------

Before runneing the notebooks, a series of Python Libaries and geophysical/hydrological modelling softwares must be installed.
The instalations needed depends on the modalites you want to use (e.g. ResiPy coupled with HYDRUS-1D).


.. code-block:: console

   (.venv) $ pip install lumache
   
.. _Synthetic geophysical data:

Synthetic geophysical data
------------


To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']
