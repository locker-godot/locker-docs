
.. _LockerPlugin:

============
LockerPlugin
============

**Inherits:** 

The :ref:`LockerPlugin <LockerPlugin>` class is the manager of the Locker Plugin's editor features.

Description
===========

This class is responsible for managing the access of the settings of this Plugin through the use of the :ref:`LokSettingsManager <LokSettingsManager>` class.
The settings of this Plugin only become available while the :ref:`LockerPlugin <LockerPlugin>` is active, though.
When active, this Plugin also registers the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` as an autoload singleton.

**Version**: 1.0.0
**Author**: github.com/nadjiel <github.com/nadjiel>_


Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`_start_plugin <LockerPlugin__start_plugin>`\(\)* - :ref:`void <void>`
     - :ref:`_finish_plugin <LockerPlugin__finish_plugin>`\(\)

Constant Descriptions
=====================

.. _LockerPlugin_AUTOLOAD_NAME:

AUTOLOAD_NAME = ``"LokGlobalStorageManager"``
---------------------------------------------

The :ref:`AUTOLOAD_NAME <AUTOLOAD_NAME>` constant stores the name that should be given to the :ref:`LockerPlugin <LockerPlugin>`'s autoload, when registered.


.. _LockerPlugin_AUTOLOAD_PATH:

AUTOLOAD_PATH = ``"res://addons/locker/scripts/storage_manager/global_storage_manager.gd"``
-------------------------------------------------------------------------------------------

The :ref:`AUTOLOAD_PATH <AUTOLOAD_PATH>` constant stores the path to the script of the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` so that this :ref:`LockerPlugin <LockerPlugin>` can register it as an autoload when it is activated.






Method Descriptions
===================


.. _LockerPlugin__start_plugin:

:ref:`void <void>` _start_plugin\(\)
------------------------------------

The :ref:`_start_plugin <_start_plugin>` method registers the singleton needed by the :ref:`LockerPlugin <LockerPlugin>` as an autoload, so it isn't needed to do that manually.
This method also updates and registers the settings of this plugin in the :ref:`ProjectSettings <ProjectSettings>`, making sure to load any settings used before deactivating this plugin.
When doing that, this method makes it so arbitrary :ref:`LokAccessStratey <LokAccessStratey>`s saved in the :ref:`LokSettingsManager.STRATEGY_SCRIPTS_PATH <LokSettingsManager_STRATEGY_SCRIPTS_PATH>` are also made available in the :ref:`ProjectSettings <ProjectSettings>` so that they can be easily selected. 
Finally, this method makes sure that whenever a setting from this Plugin is altered, it is saved in the :ref:`ConfigFile <ConfigFile>` in the :ref:`LokSettingsManager.CONFIG_PATH <LokSettingsManager_CONFIG_PATH>`.


.. _LockerPlugin__finish_plugin:

:ref:`void <void>` _finish_plugin\(\)
-------------------------------------

The :ref:`_finish_plugin <_finish_plugin>` method unregisters the singleton needed by the :ref:`LockerPlugin <LockerPlugin>` from the autoloads, so it doesn't stay there without the Plugin being active.
This method also unregisters the settings of this plugin from the :ref:`ProjectSettings <ProjectSettings>`.

