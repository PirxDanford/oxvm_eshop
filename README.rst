Overview
========

This project extends the Base VM and is optimized for specific versions of the OXID eShop.

Final solution is composed of two repositories (*linked using git sub-modules*):

* `Base VM <https://github.com/OXID-eSales/oxvm_base>`_ - Base LAMP stack
* `eShop VM <https://github.com/OXID-eSales/oxvm_eshop>`_ - Current repository, eShop specific configuration and roles.

Getting started
===============

Dependencies
------------

Please make sure that the Dependencies from the `Base VM <https://github.com/OXID-eSales/oxvm_base#dependencies>`_ are in place.

Notice
------
For OXID eShop Professional Edition or OXID eShop Enterprise Edition, you need to enter the credentials you should have received when purchasing the product.

Quick start
-----------

**Note for Windows users**: Use console with **Administrator privileges** to run vagrant commands! 

* Clone [#recursive_clone]_ out current repository:

.. code:: bash

  git clone --recursive https://github.com/OXID-eSales/oxvm_eshop.git

* Start the VM:

.. code:: bash

  cd oxvm_eshop
  vagrant up
  vagrant ssh
  cd /var/www/oxideshop
  # for the Community Edition
  composer create-project oxid-esales/oxideshop-project . dev-b-6.0-ce
  # for the Professional Edition
  composer create-project oxid-esales/oxideshop-project . dev-b-6.0-pe
  # for the Enterprise Edition
  composer create-project oxid-esales/oxideshop-project . dev-b-6.0-ee
  exit

* Set up your shop via http://www.oxideshop.dev/Setup

  * Database Name, User and Password: oxid
  * Keep track of the admin Email and Password you define

* After successful installation and setup use the following links to:

  * Open OXID eShop: http://www.oxideshop.dev/
  * Access admin area: http://www.oxideshop.dev/admin/

    * Username: Defined during the setup
    * Password: Defined during the setup

.. [#recursive_clone] Since the current eShop VM repository is linked through git sub-modules
  it is mandatory to use ``--recursive`` option to instruct ``git`` and clone
  base VM repository as well.
