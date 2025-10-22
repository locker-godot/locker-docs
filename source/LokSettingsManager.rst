
.. _LokSettingsManager:

==================
LokSettingsManager
==================

**Inherits:** 

The :ref:`LokSettingsManager <LokSettingsManager>` class provides simplified ways to manage the :ref:`LockerPlugin <LockerPlugin>` settings.

Description
===========

This class is responsible for managing the access of the :ref:`LockerPlugin <LockerPlugin>`'s settings through the use of the :ref:`ProjectSettings <ProjectSettings>`.
The settings of this Plugin stay available in the ``addons/locker`` path of the :ref:`ProjectSettings <ProjectSettings>`.
With this class, the settings exposed by the :ref:`LockerPlugin <LockerPlugin>` can be registered, unregistered, set and get from the :ref:`ProjectSettings <ProjectSettings>`.

**Version**: 1.1.2 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`Script <Script>`[]
     - :ref:`_strategy_scripts <LokSettingsManager__strategy_scripts>`
     - ``_load_strategy_scripts()``
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`_plugin_settings <LokSettingsManager__plugin_settings>`
     - ``{...}``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`set_setting_saves_directory <LokSettingsManager_set_setting_saves_directory>`\(:ref:`String <String>` path\)* - :ref:`String <String>`
     - :ref:`get_setting_saves_directory <LokSettingsManager_get_setting_saves_directory>`\(\)* - :ref:`void <void>`
     - :ref:`set_setting_save_files_prefix <LokSettingsManager_set_setting_save_files_prefix>`\(:ref:`String <String>` prefix\)* - :ref:`String <String>`
     - :ref:`get_setting_save_files_prefix <LokSettingsManager_get_setting_save_files_prefix>`\(\)* - :ref:`void <void>`
     - :ref:`set_setting_save_files_format <LokSettingsManager_set_setting_save_files_format>`\(:ref:`String <String>` format\)* - :ref:`String <String>`
     - :ref:`get_setting_save_files_format <LokSettingsManager_get_setting_save_files_format>`\(\)* - :ref:`void <void>`
     - :ref:`set_setting_save_versions <LokSettingsManager_set_setting_save_versions>`\(:ref:`bool <bool>` state\)* - :ref:`bool <bool>`
     - :ref:`get_setting_save_versions <LokSettingsManager_get_setting_save_versions>`\(\)* - :ref:`void <void>`
     - :ref:`set_setting_access_strategy <LokSettingsManager_set_setting_access_strategy>`\(:ref:`String <String>` strategy\)* - :ref:`String <String>`
     - :ref:`get_setting_access_strategy <LokSettingsManager_get_setting_access_strategy>`\(\)* - :ref:`LokAccessStrategy <LokAccessStrategy>`
     - :ref:`get_setting_access_strategy_parsed <LokSettingsManager_get_setting_access_strategy_parsed>`\(\)* - :ref:`void <void>`
     - :ref:`set_setting_encrypted_strategy_password <LokSettingsManager_set_setting_encrypted_strategy_password>`\(:ref:`String <String>` password\)* - :ref:`String <String>`
     - :ref:`get_setting_encrypted_strategy_password <LokSettingsManager_get_setting_encrypted_strategy_password>`\(\)* - :ref:`void <void>`
     - :ref:`update_available_strategies <LokSettingsManager_update_available_strategies>`\(\)* - :ref:`void <void>`
     - :ref:`save_settings <LokSettingsManager_save_settings>`\(:ref:`Dictionary <Dictionary>` settings\)* - :ref:`void <void>`
     - :ref:`load_settings <LokSettingsManager_load_settings>`\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`get_changed_settings <LokSettingsManager_get_changed_settings>`\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)* - :ref:`void <void>`
     - :ref:`add_settings <LokSettingsManager_add_settings>`\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)* - :ref:`void <void>`
     - :ref:`remove_settings <LokSettingsManager_remove_settings>`\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)* - :ref:`Script <Script>`[]
     - :ref:`_load_strategy_scripts <LokSettingsManager__load_strategy_scripts>`\(\)* - :ref:`LokAccessStrategy <LokAccessStrategy>`[]
     - :ref:`_get_strategies <LokSettingsManager__get_strategies>`\(\)* - :ref:`String <String>`
     - :ref:`_get_strategies_enum_string <LokSettingsManager__get_strategies_enum_string>`\(\)* - :ref:`String <String>`
     - :ref:`_get_default_strategy_name <LokSettingsManager__get_default_strategy_name>`\(:ref:`String <String>` wanted_name\)* - :ref:`LokAccessStrategy <LokAccessStrategy>`
     - :ref:`_string_to_strategy <LokSettingsManager__string_to_strategy>`\(:ref:`String <String>` string\)* - :ref:`String <String>`
     - :ref:`_strategy_to_string <LokSettingsManager__strategy_to_string>`\(:ref:`LokAccessStrategy <LokAccessStrategy>` strategy\)

Constant Descriptions
=====================

.. _LokSettingsManager_CONFIG_PATH:

CONFIG_PATH = ``"res://addons/locker/config.cfg"``
--------------------------------------------------

The :ref:`CONFIG_PATH <CONFIG_PATH>` constant stores the path where the :ref:`LockerPlugin <LockerPlugin>`'s configurations should be stored, so that they can be persisted even when the Plugin is deactivated and activated again.


.. _LokSettingsManager_STRATEGY_SCRIPTS_PATH:

STRATEGY_SCRIPTS_PATH = ``"res://addons/locker/scripts/access_strategy/default_strategies/"``
---------------------------------------------------------------------------------------------

The :ref:`STRATEGY_SCRIPTS_PATH <STRATEGY_SCRIPTS_PATH>` constant stores the path to where the scripts of :ref:`LokAccessStrategy <LokAccessStrategy>`s are located.
It's the :ref:`LokAccessStrategy <LokAccessStrategy>`s declared in that folder that are exposed to be selectable in the :ref:`ProjectSettings <ProjectSettings>` as :ref:`LokAccessStrategy <LokAccessStrategy>`s to be used by this plugin.





Property Descriptions
=====================


.. _LokSettingsManager__strategy_scripts:

:ref:`Script <Script>`[] _strategy_scripts = ``_load_strategy_scripts()``
-------------------------------------------------------------------------

The :ref:`_strategy_scripts <_strategy_scripts>` property stores references to the :ref:`Script <Script>`s of the :ref:`LokAccessStrategy <LokAccessStrategy>`s that the :ref:`LockerPlugin <LockerPlugin>` knows thanks to the path in the :ref:`STRATEGY_SCRIPTS_PATH <STRATEGY_SCRIPTS_PATH>` constant.


.. _LokSettingsManager__plugin_settings:

:ref:`Dictionary <Dictionary>` _plugin_settings = ``{...}``
-----------------------------------------------------------

The :ref:`_plugin_settings <_plugin_settings>` property stores a :ref:`Dictionary <Dictionary>` that describes all the settings that should be appended to the :ref:`ProjectSettings <ProjectSettings>` when the :ref:`LockerPlugin <LockerPlugin>` is activated, so that they can be easily edited through the editor.
Each key of this :ref:`Dictionary <Dictionary>` points to the setting path in the :ref:`ProjectSettings <ProjectSettings>` and each value describes information about the setting.
The structure of this property is as follows:
.. codeblock:: gdscript 


   {
     "setting_1_path": {
       "default_value": <Variant>,
       "current_value": <Variant>,
       "is_basic": <bool>,
       "property_info": {
         "name": "setting_1_path",
         "type": <@GlobalScope.Variant.Type>,
         "hint": <@GlobalScope.PropertyHint>,
         "hint_string": <String>
       },
       "config_section": <String>,
     },
     "setting_n_path": { ... }
   }

The settings defined in this property are the following:
- ``"addons/locker/saves_directory"``: This setting defines the default directory where the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` should save and load the game data.
- ``"addons/locker/save_files_prefix"``: This setting defines the default prefix that should be given to the save files by the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>`.
- ``"addons/locker/save_files_format"``: This setting defines the default file format that should be given to the save files by the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>`.
- ``"addons/locker/save_versions"``: This setting defines if, by default, the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` should store the save versions when saving.
- ``"addons/locker/access_strategy"``: This setting stores a :ref:`String <String>` that represents what :ref:`LokAccessStrategy <LokAccessStrategy>` the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` should use to save and load data. To convert from this :ref:`String <String>` representation to an actual :ref:`LokAccessStrategy <LokAccessStrategy>` instance, the :ref:`_string_to_strategy <_string_to_strategy>` method can be used.
- ``"addons/locker/encrypted_strategy/password"``: This setting stores the default password that should be used by the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>`'s strategy, if it is the :ref:`LokEncryptedAccessStrategy <LokEncryptedAccessStrategy>`.



Method Descriptions
===================


.. _LokSettingsManager_set_setting_saves_directory:

:ref:`void <void>` set_setting_saves_directory\(:ref:`String <String>` path\)
-----------------------------------------------------------------------------

The :ref:`set_setting_saves_directory <set_setting_saves_directory>` method is a shortcut to defining the ``"addons/locker/saves_directory"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``path``.


.. _LokSettingsManager_get_setting_saves_directory:

:ref:`String <String>` get_setting_saves_directory\(\)
------------------------------------------------------

The :ref:`get_setting_saves_directory <get_setting_saves_directory>` method is a getter to facilitate obtaining the ``"addons/locker/saves_directory"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_set_setting_save_files_prefix:

:ref:`void <void>` set_setting_save_files_prefix\(:ref:`String <String>` prefix\)
---------------------------------------------------------------------------------

The :ref:`set_setting_save_files_prefix <set_setting_save_files_prefix>` method is a shortcut to defining the ``"addons/locker/save_files_prefix"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``prefix``.


.. _LokSettingsManager_get_setting_save_files_prefix:

:ref:`String <String>` get_setting_save_files_prefix\(\)
--------------------------------------------------------

The :ref:`get_setting_save_files_prefix <get_setting_save_files_prefix>` method is a getter to facilitate obtaining the ``"addons/locker/save_files_prefix"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_set_setting_save_files_format:

:ref:`void <void>` set_setting_save_files_format\(:ref:`String <String>` format\)
---------------------------------------------------------------------------------

The :ref:`set_setting_save_files_format <set_setting_save_files_format>` method is a shortcut to defining the ``"addons/locker/save_files_format"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``format``.


.. _LokSettingsManager_get_setting_save_files_format:

:ref:`String <String>` get_setting_save_files_format\(\)
--------------------------------------------------------

The :ref:`get_setting_save_files_format <get_setting_save_files_format>` method is a getter to facilitate obtaining the ``"addons/locker/save_files_format"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_set_setting_save_versions:

:ref:`void <void>` set_setting_save_versions\(:ref:`bool <bool>` state\)
------------------------------------------------------------------------

The :ref:`set_setting_save_versions <set_setting_save_versions>` method is a shortcut to defining the ``"addons/locker/save_versions"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``state``.


.. _LokSettingsManager_get_setting_save_versions:

:ref:`bool <bool>` get_setting_save_versions\(\)
------------------------------------------------

The :ref:`get_setting_save_versions <get_setting_save_versions>` method is a getter to facilitate obtaining the ``"addons/locker/save_versions"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_set_setting_access_strategy:

:ref:`void <void>` set_setting_access_strategy\(:ref:`String <String>` strategy\)
---------------------------------------------------------------------------------

The :ref:`set_setting_access_strategy <set_setting_access_strategy>` method is a shortcut to defining the ``"addons/locker/access_strategy"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``strategy``.


.. _LokSettingsManager_get_setting_access_strategy:

:ref:`String <String>` get_setting_access_strategy\(\)
------------------------------------------------------

The :ref:`get_setting_access_strategy <get_setting_access_strategy>` method is a getter to facilitate obtaining the ``"addons/locker/access_strategy"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_get_setting_access_strategy_parsed:

:ref:`LokAccessStrategy <LokAccessStrategy>` get_setting_access_strategy_parsed\(\)
-----------------------------------------------------------------------------------

The :ref:`get_setting_access_strategy_parsed <get_setting_access_strategy_parsed>` method is a getter to facilitate obtaining the ``"addons/locker/access_strategy"`` setting from the :ref:`ProjectSettings <ProjectSettings>` already parsed as a :ref:`LokAccessStrategy <LokAccessStrategy>`.


.. _LokSettingsManager_set_setting_encrypted_strategy_password:

:ref:`void <void>` set_setting_encrypted_strategy_password\(:ref:`String <String>` password\)
---------------------------------------------------------------------------------------------

The :ref:`set_setting_encrypted_strategy_password <set_setting_encrypted_strategy_password>` method is a shortcut to defining the ``"addons/locker/encrypted_strategy/password"`` setting in the :ref:`ProjectSettings <ProjectSettings>` to the value of the passed ``password``.


.. _LokSettingsManager_get_setting_encrypted_strategy_password:

:ref:`String <String>` get_setting_encrypted_strategy_password\(\)
------------------------------------------------------------------

The :ref:`get_setting_encrypted_strategy_password <get_setting_encrypted_strategy_password>` method is a getter to facilitate obtaining the ``"addons/locker/encrypted_strategy/password"`` setting from the :ref:`ProjectSettings <ProjectSettings>`.


.. _LokSettingsManager_update_available_strategies:

:ref:`void <void>` update_available_strategies\(\)
--------------------------------------------------

The :ref:`update_available_strategies <update_available_strategies>` method uses the :ref:`_strategy_scripts <_strategy_scripts>` to update what :ref:`LokAccessStrategy <LokAccessStrategy>` options should be shown in the :ref:`ProjectSettings <ProjectSettings>` as options to choose from.


.. _LokSettingsManager_save_settings:

:ref:`void <void>` save_settings\(:ref:`Dictionary <Dictionary>` settings\)
---------------------------------------------------------------------------

The :ref:`save_settings <save_settings>` method takes a ``settings`` :ref:`Dictionary <Dictionary>` and takes the current value of each one of them from the :ref:`ProjectSettings <ProjectSettings>`, saving them in a :ref:`ConfigFile <ConfigFile>` in the :ref:`CONFIG_PATH <CONFIG_PATH>`.
The ``settings`` parameter has to conform to the structure explained in the :ref:`_plugin_settings <_plugin_settings>` description.


.. _LokSettingsManager_load_settings:

:ref:`void <void>` load_settings\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)
--------------------------------------------------------------------------------------------------

The :ref:`load_settings <load_settings>` method takes a ``settings`` :ref:`Dictionary <Dictionary>` and loads the settings described by it from the :ref:`ConfigFile <ConfigFile>` in the :ref:`CONFIG_PATH <CONFIG_PATH>`. This method, then, sets the loaded settings in the :ref:`ProjectSettings <ProjectSettings>`.
The ``settings`` parameter has to conform to the structure explained in the :ref:`_plugin_settings <_plugin_settings>` description.


.. _LokSettingsManager_get_changed_settings:

:ref:`Dictionary <Dictionary>` get_changed_settings\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)
---------------------------------------------------------------------------------------------------------------------

The :ref:`get_changed_settings <get_changed_settings>` method takes a ``settings`` :ref:`Dictionary <Dictionary>` and looks for settings that had their values changed.
When found, their values are updated and they are returned. The ``settings`` parameter as well as the returned :ref:`Dictionary <Dictionary>` conform to the structure explained in the :ref:`_plugin_settings <_plugin_settings>` description.


.. _LokSettingsManager_add_settings:

:ref:`void <void>` add_settings\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)
-------------------------------------------------------------------------------------------------

The :ref:`add_settings <add_settings>` method takes a ``settings`` :ref:`Dictionary <Dictionary>` and saves each of its settings in the :ref:`ProjectSettings <ProjectSettings>`.
The ``settings`` parameter must conform to the structure explained in the :ref:`_plugin_settings <_plugin_settings>` description.


.. _LokSettingsManager_remove_settings:

:ref:`void <void>` remove_settings\(:ref:`Dictionary <Dictionary>` settings = ``_plugin_settings``\)
----------------------------------------------------------------------------------------------------

The :ref:`remove_settings <remove_settings>` method takes a ``settings`` :ref:`Dictionary <Dictionary>` and removes each of its settings from the :ref:`ProjectSettings <ProjectSettings>`.
The ``settings`` parameter must conform to the structure explained in the :ref:`_plugin_settings <_plugin_settings>` description.


.. _LokSettingsManager__load_strategy_scripts:

:ref:`Script <Script>`[] _load_strategy_scripts\(\)
---------------------------------------------------

The :ref:`_load_strategy_scripts <_load_strategy_scripts>` method returns an :ref:`Array <Array>` of :ref:`Script <Script>`s with the scripts that could be found in the path pointed by the :ref:`STRATEGY_SCRIPTS_PATH <STRATEGY_SCRIPTS_PATH>` constant.


.. _LokSettingsManager__get_strategies:

:ref:`LokAccessStrategy <LokAccessStrategy>`[] _get_strategies\(\)
------------------------------------------------------------------

The :ref:`_get_strategies <_get_strategies>` method returns an :ref:`Array <Array>` of :ref:`LokAccessStrategy <LokAccessStrategy>` instances got from the :ref:`Script <Script>`s in the :ref:`_strategy_scripts <_strategy_scripts>` property.


.. _LokSettingsManager__get_strategies_enum_string:

:ref:`String <String>` _get_strategies_enum_string\(\)
------------------------------------------------------

The :ref:`_get_strategies_enum_string <_get_strategies_enum_string>` method parses the :ref:`LokAccessStrategy <LokAccessStrategy>`s that the :ref:`LockerPlugin <LockerPlugin>` knows into a :ref:`String <String>` that describes them in a way compatible with ``hint_string``s.


.. _LokSettingsManager__get_default_strategy_name:

:ref:`String <String>` _get_default_strategy_name\(:ref:`String <String>` wanted_name\)
---------------------------------------------------------------------------------------

The :ref:`_get_default_strategy_name <_get_default_strategy_name>` method tries to get the name of the :ref:`LokAccessStrategy <LokAccessStrategy>` specified by the ``wanted_name`` parameter, so that name can be used in the :ref:`ProjectSettings <ProjectSettings>` as the default choice in the strategies enum.
If there's no such :ref:`LokAccessStrategy <LokAccessStrategy>` known by the :ref:`LockerPlugin <LockerPlugin>`, this method will return any :ref:`LokAccessStrategy <LokAccessStrategy>` name it knows, or even an empty :ref:`String <String>`, if it doesn't know any :ref:`LokAccessStrategy <LokAccessStrategy>`s.


.. _LokSettingsManager__string_to_strategy:

:ref:`LokAccessStrategy <LokAccessStrategy>` _string_to_strategy\(:ref:`String <String>` string\)
-------------------------------------------------------------------------------------------------

The :ref:`_string_to_strategy <_string_to_strategy>` method takes a ``string`` and returns a :ref:`LokAccessStrategy <LokAccessStrategy>` that corresponds to that ``string``.
If an invalid ``string`` is passed, this method returns ``null``.


.. _LokSettingsManager__strategy_to_string:

:ref:`String <String>` _strategy_to_string\(:ref:`LokAccessStrategy <LokAccessStrategy>` strategy\)
---------------------------------------------------------------------------------------------------

The :ref:`_strategy_to_string <_strategy_to_string>` method takes a ``strategy`` and returns a :ref:`String <String>` that represents that ``strategy`` in the ``"addons/locker/access_strategy"`` setting of the :ref:`ProjectSettings <ProjectSettings>`.
If an invalid ``strategy`` is passed, this method returns an empty :ref:`String <String>`.

