IViS
======

**IViS** — Interferometric Visibility-space Inversion Software

IViS is a fast, GPU-accelerated non-linear deconvolution tool for radio interferometry, scalable to large mosaics and hyperspectral cubes.

Because of its intrinsic framework based on a regularized criterion, IViS — like MEM — is better suited for diffuse emission rather than point sources, whose flux tends to be spread by the regularizer. IViS was developed in the context of imaging H I spectral line data from the ASKAP and MeerKAT instruments.

IViS is designed as a modular framework upon which new deconvolution methods can be built.

.. note::

   In its current implementation, IViS is a generic MEM-like mosaicking framework (with no w-term), but it aims to incorporate arbitrary spectral models in the near future to fully exploit the spectral dimension of the data.
   IViS is very new, and this documentation is in its early stages — it will continue to evolve as the project develops.

Useful resources:
- `Github repository <https://github.com/antoinemarchal/ivis>`_

.. note::
   
   Parts of this code were inspired by the `MPol <https://github.com/MPoL-dev/MPoL>`_ package,
   which implements a Regularized Maximum Likelihood (RML) framework for radio interferometric imaging.
   In contrast to `MPol <https://github.com/MPoL-dev/MPoL>`_, IViS includes native support for image-plane mosaicking with DDEs of the Primary Beam.


Installation
------------

To get started, we recommend using ``uv`` to manage packages and ``mamba`` to create a clean environment with `casacore`:

.. code-block:: bash

   # Install mamba (if not already available)
   conda install mamba -n base -c conda-forge

   # Create the IViS environment
   mamba create -n ivis \
     python=3.10 casacore=3.4.0 python-casacore=3.4.0 gsl=2.6 pip \
     -c conda-forge -c pkgs/main

   mamba activate ivis

   # Install uv (if not already available)
   curl -LsSf https://astral.sh/uv/install.sh | sh
   export PATH="$HOME/.cargo/bin:$PATH"  # if needed

   # Install IViS and dependencies using uv
   uv pip install git+https://github.com/antoinemarchal/ivis.git

.. note::

   To delete an environment:

   .. code-block:: bash

      mamba env remove -n ivis

Models
------

.. toctree::
   :maxdepth: 1
   :caption: Forward models:

   models/single
   models/gmfs


Tutorials
---------

.. toctree::
   :maxdepth: 1
   :caption: Basics:

   tutorials/get_started

API Reference
-------------

.. toctree::
   :maxdepth: 1
   :caption: API:

   api

.. note::

   If you use **IViS**, please cite our work and reference the
   `IViS GitHub repository <https://github.com/antoinemarchal/ivis>`_.
