Alignak checks package for Alignak daemons
==========================================

*Checks pack for monitoring Alignak daemons with the Nagios monitoring check_tcp*


.. image:: https://badge.fury.io/py/alignak_checks_alignak.svg
    :target: https://badge.fury.io/py/alignak-checks-alignak
    :alt: Most recent PyPi version

.. image:: https://img.shields.io/badge/IRC-%23alignak-1e72ff.svg?style=flat
    :target: http://webchat.freenode.net/?channels=%23alignak
    :alt: Join the chat #alignak on freenode.net

.. image:: https://img.shields.io/badge/License-AGPL%20v3-blue.svg
    :target: http://www.gnu.org/licenses/agpl-3.0
    :alt: License AGPL v3


**Note:** *this check pack is only an example for checking Alignak daemons using the Nagios check_tcp command. Please feel free to comment or suggest improvements :)*


Installation
------------

The installation of this checks pack will copy some configuration files in the Alignak default configuration directory (eg. */usr/local/etc/alignak*). The copied files are located in the default sub-directory used for the packs (eg. *arbiter/packs*).

From PyPI
~~~~~~~~~
To install the package from PyPI:
::

   sudo pip install alignak-checks-alignak


From source files
~~~~~~~~~~~~~~~~~
To install the package from the source files:
::

   git clone https://github.com/Alignak-monitoring-contrib/alignak-checks-alignak
   cd alignak-checks-alignak
   sudo pip install .

**Note:** *using `sudo python setup.py install` will not correctly manage the package configuration files! The recommended way is really to use `pip`;)*

Documentation
-------------

Configuration
~~~~~~~~~~~~~

This checks pack is using the `check_tcp` Nagios (or Monitoring) plugin that must be installed on the Alignak server running your poller daemon. You may install the `alignak-checks-monitoring` package (see the `corresponding repo <https://github.com/alignak-monitoring-contrib/alignak-checks-monitoring/issues>`_).



Alignak configuration
~~~~~~~~~~~~~~~~~~~~~

For a Linux monitored host, you simply have to tag the concerned host with the template ``linux-nrpe``.
::

    # An host with all Alignak daemons except the arbiter
    define host{
        use                     alignak
        host_name               my_alignak
        address                 127.0.0.1
    }

    # An host with all the Alignak daemons
    define host{
        use                     alignak-main
        host_name               my_alignak
        address                 127.0.0.1
    }



Bugs, issues and contributing
-----------------------------

Contributions to this project are welcome and encouraged ... `issues in the project repository <https://github.com/alignak-monitoring-contrib/alignak-checks-alignak/issues>`_ are the common way to raise an information.
