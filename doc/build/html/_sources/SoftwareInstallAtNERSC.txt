####################################
NERSC Software Installation for DESC
####################################

.. tip:: **Quick Start for DMstack users**

   - **Cori:** 
     source /global/common/cori/contrib/lsst/lsstDM/setupStack-dc1.sh 

   - **Edison:** 
     source /global/common/edison/contrib/lsst/lsstDM/setupStack-dc1.sh

Software Installation Locations
=================================
.. note::
   - Cori:   /global/common/cori/contrib/lsst
   - Edison: /global/common/edison/contrib/lsst

DMStack
==================================

+-----------+---------------------------------------------------------------+-----------------+--------------------------------------------------+
| Version   |     Cori                                                      |  Notes          |       Edison                                     |   
+===========+===============================================================+=================+==================================================+
| dc1       |/global/common/cori/contrib/lsst/lsstDM/dc1                    |30 Jan 2017      |                                                  |
|           |/global/common/cori/contrib/lsst-lsstDM/setupStack-dc1.sh      |                 |                                                  |
+-----------+---------------------------------------------------------------+-----------------+--------------------------------------------------+
| 12_1      |/global/common/cori/contrib/lsst/lsstDM/v12_1                  |29 Nov 2016      |                                                  |
| Twinkles  |                                                               |Update obsSim    |                                                  |
| Run 3.1-a |/global/common/cori/contrib/lsst/lsstDM/setupStack-Run3.1-a.sh |12.1-20-g13741e2 |                                                  |
+-----------+---------------------------------------------------------------+-----------------+--------------------------------------------------+
| 12_1      |/global/common/cori/contrib/lsst/lsstDM/v12_1                  |20 Nov 2016      |                                                  |
| Twinkles  |                                                               |Update obsSim    |                                                  |
| Run 3.1   |/global/common/cori/contrib/lsst/lsstDM/setupStack-Run3.1.sh   |12.1-10-g0a95c5d |                                                  |
+-----------+---------------------------------------------------------------+-----------------+--------------------------------------------------+
| 12_1      |/global/common/cori/contrib/lsst/lsstDM/v12_1                  | 8 Nov 2016      |                                                  |
|           |                                                               | Vanilla 12_1    |/global/common/edison/contrib/lsst/lsstDM/v12_1   |
+-----------+---------------------------------------------------------------+-----------------+--------------------------------------------------+


Setup for Bash Shell Users
----------------------------------
.. code-block:: bash
   :name: setup-dmstack 

   source <PathToInstallation>/setupStack-<Version>.sh [-v]


Phosim
===================================

+---------+----------------------------------------------------+---------------------------------------------------+
| Version |     Cori Directory                                 | Edison Directory                                  |   
+=========+====================================================+===================================================+
| v3.6    |/global/common/cori/contrib/lsst/phosim/v3.6        | /global/common/edison/contrib/lsst/phosim/v3.6    |
+---------+----------------------------------------------------+---------------------------------------------------+


Setup for Bash Shell Users
------------------------------------------

.. code-block:: bash
   :name: setup-phosim 

   source <PathToInstallationDirectory>/setupPhosim.sh

Now the environment is set up to run any version of phosim available under its installation directory i.e.  v3.6

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

.. code-block:: bash
   :name: source-install-instructions

    unset LSST_HOME EUPS_PATH LSST_DEVEL EUPS_PKGROOT REPOSITORY_PATH
    curl -OL https://raw.githubusercontent.com/lsst/lsst/12.0/scripts/newinstall.sh
    bash newinstall.sh
    source loadLSST.bash
    eups distrib install -t <tag> lsst_apps --nolocks
    eups distrib install -t <tag> lsst_sims --nolocks





Phosim Installation Instructions
------------------------------------
