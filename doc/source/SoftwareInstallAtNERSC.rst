####################################
NERSC Software Installation for DESC
####################################

.. IMPORTANT::
   Cori will be down for approximately the next 6 weeks. Please use Edison during this time.

Software Installation Location
=================================
- Cori:   /global/common/cori/contrib/lsst
- Edison: /global/common/edison/contrib/lsst

DMStack
==================================

Installed Versions
----------------------------------

- 20160907 most recent installation using the sims conda channel
- v12_0  official DMstack release


Cori: /global/common/cori/contrib/lsst/lsstDM

Edison: /global/common/edison/contrib/lsst/lsstDM

Setup for Bash Shell Users
----------------------------------
.. code-block:: bash
   :name: setup-dmstack 

   source <PathToInstallation>/setupStack-<Version>.sh [-v]

The above will update your environment to use the conda environment installed with DMstack.  To exit and reset your environment, at the 
command line do:
"source deactivate"

Phosim
===================================

Installed Versions
------------------------------------

- v3.5.3
- v3.5.2

Cori: /global/common/cori/contrib/lsst/phosim

Edison: /global/common/edison/contrib/lsst/phosim

Setup for Bash Shell Users
------------------------------------------

.. code-block:: bash
   :name: setup-phosim 

   source <PathToInstallationDirectory>/setupPhosim.sh

run any version of phosim available under its installation directory i.e.  v3.5.3

Notes for Installation Maintainers 
===================================

DMstack Installation Instructions
----------------------------------
When possible we use the sims conda channel

.. code-block:: bash
   :name: conda-install-instructions
   
   module swap PrgEnv-intel PrgEnv-gnu
   module swap gcc gcc/4.9.3
   module load python/2.7-anaconda
   export CONDA_ENVS_PATH=$PWD/envs
   conda create --prefix /global/common/edison/contrib/lsst/lsstDM/<date>
   --channel http://conda.lsst.codes/sims python=2 lsst-apps
   source activate /global/common/edison/contrib/lsst/lsstDM/<date>
   conda install --channel http://conda.lsst.codes/sims lsst-sims

Phosim Installation Instructions
------------------------------------
