####################################
NERSC Software Installation for DESC
####################################

.. tip:: **Quick Start for DMstack users**

   - **Cori:** 
     source /global/common/cori/contrib/lsst/lsstDM/setupStack-12_1.sh 

   - **Edison:** 
     source /global/common/edison/contrib/lsst/lsstDM/setupStack-12_1.sh

Software Installation Locations
=================================
.. note::
   - Cori:   /global/common/cori/contrib/lsst
   - Edison: /global/common/edison/contrib/lsst

DMStack
==================================

+---------+----------------------------------------------------+---------------------------------------------------+
| Version |     Cori Directory                                 | Edison Directory                                  |   
+=========+====================================================+===================================================+
| 12_1    |/global/common/cori/contrib/lsst/lsstDM/v12_1       | /global/common/edison/contrib/lsst/lsstDM/v12_1   |
+---------+----------------------------------------------------+---------------------------------------------------+


Setup for Bash Shell Users
----------------------------------
.. code-block:: bash
   :name: setup-dmstack 

   source <PathToInstallation>/setupStack-<Version>.sh [-v]

The above will update your environment to use the conda environment installed with DMstack. You may then "setup" any DMstack or sims packages as usual:

.. code-block:: bash
   :name: setup-lsst_apps

   source /global/common/cori/contrib/lsst/lsstDM/setupStack-12_1.sh
   setup lsst_apps

Phosim
===================================

+---------+----------------------------------------------------+---------------------------------------------------+
| Version |     Cori Directory                                 | Edison Directory                                  |   
+=========+====================================================+===================================================+
| v3.5.3  |/global/common/cori/contrib/lsst/phosim/v3.5.3      | /global/common/edison/contrib/lsst/phosim/v3.5.3  |
+---------+----------------------------------------------------+---------------------------------------------------+


Setup for Bash Shell Users
------------------------------------------

.. code-block:: bash
   :name: setup-phosim 

   source <PathToInstallationDirectory>/setupPhosim.sh

Now the environment is set up to run any version of phosim available under its installation directory i.e.  v3.5.3

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

Installation from Source


Phosim Installation Instructions
------------------------------------
