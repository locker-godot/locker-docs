
.. _LokGlobalStorageManager:

=======================
LokGlobalStorageManager
=======================

**Inherits:** 

The :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` class is the main manager of the manipulation processes.

Description
===========

This class is registered as an autoload when the :ref:`LockerPlugin <LockerPlugin>` is active, so that it can do its tasks. 
It's this class that's responsible for keeping track of all the :ref:`LokStorageAccessor <LokStorageAccessor>`s in the current scene tree, so that they can easily save and load their data. 

**Version**: 1.0.0 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`String <String>`
     - :ref:`saves_directory <LokGlobalStorageManager_saves_directory>`
     - ``get_setting_saves_directory()``
   * - :ref:`String <String>`
     - :ref:`save_files_prefix <LokGlobalStorageManager_save_files_prefix>`
     - ``get_setting_save_files_prefix()``
   * - :ref:`String <String>`
     - :ref:`save_files_format <LokGlobalStorageManager_save_files_format>`
     - ``get_setting_save_files_format()``
   * - :ref:`bool <bool>`
     - :ref:`save_versions <LokGlobalStorageManager_save_versions>`
     - ``get_setting_save_versions()``
   * - :ref:`LokAccessExecutor <LokAccessExecutor>`
     - :ref:`_access_executor <LokGlobalStorageManager__access_executor>`
     - ``new()``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`set_access_strategy <LokGlobalStorageManager_set_access_strategy>`\(:ref:`LokAccessStrategy <LokAccessStrategy>` new_strategy\)* - :ref:`LokAccessStrategy <LokAccessStrategy>`
     - :ref:`get_access_strategy <LokGlobalStorageManager_get_access_strategy>`\(\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`collect_data <LokGlobalStorageManager_collect_data>`\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor, :ref:`String <String>` version_number = ``""``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`gather_data <LokGlobalStorageManager_gather_data>`\(:ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>` version_number = ``""``\)* - :ref:`void <void>`
     - :ref:`distribute_result <LokGlobalStorageManager_distribute_result>`\(:ref:`Dictionary <Dictionary>` result, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``\)* - :ref:`String <String>`[]
     - :ref:`get_saved_files_ids <LokGlobalStorageManager_get_saved_files_ids>`\(\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`save_data <LokGlobalStorageManager_save_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`load_data <LokGlobalStorageManager_load_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`read_data <LokGlobalStorageManager_read_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`remove_data <LokGlobalStorageManager_remove_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`String <String>`[]
     - :ref:`_get_accessor_ids <LokGlobalStorageManager__get_accessor_ids>`\(:ref:`LokStorageAccessor <LokStorageAccessor>`[] from_accessors\)* - :ref:`String <String>`
     - :ref:`_get_file_name <LokGlobalStorageManager__get_file_name>`\(:ref:`String <String>` file_id\)* - :ref:`String <String>`
     - :ref:`_get_file_path <LokGlobalStorageManager__get_file_path>`\(:ref:`String <String>` file_id\)* - :ref:`void <void>`
     - :ref:`_push_error_no_executor <LokGlobalStorageManager__push_error_no_executor>`\(\)




Property Descriptions
=====================


.. _LokGlobalStorageManager_saves_directory:

:ref:`String <String>` saves_directory = ``get_setting_saves_directory()``
--------------------------------------------------------------------------

The :ref:`saves_directory <saves_directory>` property stores a :ref:`String <String>` pointing to the directory where the save files should be accessed. 
By default, this property initializes with the value from the ``"addons/locker/saves_directory"`` setting in the :ref:`ProjectSettings <ProjectSettings>` (which is created by the :ref:`LockerPlugin <LockerPlugin>` using the :ref:`LokSettingsManager <LokSettingsManager>`).


.. _LokGlobalStorageManager_save_files_prefix:

:ref:`String <String>` save_files_prefix = ``get_setting_save_files_prefix()``
------------------------------------------------------------------------------

The :ref:`save_files_prefix <save_files_prefix>` property stores a :ref:`String <String>` that tells what's the prefix that should be used in the save files when creating them. 
By default, this property initializes with the value from the ``"addons/locker/save_files_prefix"`` setting in the :ref:`ProjectSettings <ProjectSettings>` (which is created by the :ref:`LockerPlugin <LockerPlugin>` using the :ref:`LokSettingsManager <LokSettingsManager>`).


.. _LokGlobalStorageManager_save_files_format:

:ref:`String <String>` save_files_format = ``get_setting_save_files_format()``
------------------------------------------------------------------------------

The :ref:`save_files_format <save_files_format>` property stores a :ref:`String <String>` that tells what's the format that should be used in the save files when accessing them. 
By default, this property initializes with the value from the ``"addons/locker/save_files_format"`` setting in the :ref:`ProjectSettings <ProjectSettings>` (which is created by the :ref:`LockerPlugin <LockerPlugin>` using the :ref:`LokSettingsManager <LokSettingsManager>`).


.. _LokGlobalStorageManager_save_versions:

:ref:`bool <bool>` save_versions = ``get_setting_save_versions()``
------------------------------------------------------------------

The :ref:`save_versions <save_versions>` property stores a ``bool`` that tells if the save files should store data about the version used when saving them, which is useful for easily versioning the saves using :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s. 
By default, this property initializes with the value from the ``"addons/locker/save_versions"`` setting in the :ref:`ProjectSettings <ProjectSettings>` (which is created by the :ref:`LockerPlugin <LockerPlugin>` using the :ref:`LokSettingsManager <LokSettingsManager>`).


.. _LokGlobalStorageManager__access_executor:

:ref:`LokAccessExecutor <LokAccessExecutor>` _access_executor = ``new()``
-------------------------------------------------------------------------

The :ref:`_access_executor <_access_executor>` property stores a :ref:`LokAccessExecutor <LokAccessExecutor>` that is responsible for separating the save files' operations in a separate :ref:`Thread <Thread>` so that they can be used asynchronously.



Method Descriptions
===================


.. _LokGlobalStorageManager_set_access_strategy:

:ref:`void <void>` set_access_strategy\(:ref:`LokAccessStrategy <LokAccessStrategy>` new_strategy\)
---------------------------------------------------------------------------------------------------

The :ref:`set_access_strategy <set_access_strategy>` method allows quickly setting the :ref:`LokAccessStrategy <LokAccessStrategy>` of the :ref:`_access_executor <_access_executor>`, if it is not ``null``.


.. _LokGlobalStorageManager_get_access_strategy:

:ref:`LokAccessStrategy <LokAccessStrategy>` get_access_strategy\(\)
--------------------------------------------------------------------

The :ref:`get_access_strategy <get_access_strategy>` method allows quickly getting the :ref:`LokAccessStrategy <LokAccessStrategy>` of the :ref:`_access_executor <_access_executor>`.


.. _LokGlobalStorageManager_collect_data:

:ref:`Dictionary <Dictionary>` collect_data\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor, :ref:`String <String>` version_number = ``""``\)
------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`collect_data <collect_data>` method is used to get and organize the data from an ``accessor``. 
Optionally, a ``version_number`` can be passed to dictate from which version of the ``accessor`` the data should be got. If left undefined, this parameter defaults to the latest available. 
At the end, this method returns a :ref:`Dictionary <Dictionary>` with all the data obtained from the ``accessor``. 
That :ref:`Dictionary <Dictionary>` is guaranteed to have a ``"version"`` key saying what version was used to get that data **IF** the :ref:`save_versions <save_versions>` property is ``true``.


.. _LokGlobalStorageManager_gather_data:

:ref:`Dictionary <Dictionary>` gather_data\(:ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>` version_number = ``""``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`gather_data <gather_data>` method is the central point where the data from all :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` is collected using the :ref:`collect_data <collect_data>` method. 
If the ``included_accessors`` parameter is not empty, this method only gathers data from the :ref:`LokStorageAccessor <LokStorageAccessor>`s that are present in that :ref:`Array <Array>`. 
The ``version_number`` parameter is used as the version of the :ref:`LokStorageAccessor <LokStorageAccessor>`s from which the data is collected. If left undefined, this parameter defaults to an empty :ref:`String <String>`, which converts to their latest version. 
In the case there's :ref:`LokStorageAccessor.id <LokStorageAccessor_id>` conflicts in the same :ref:`LokStorageAccessor.partition <LokStorageAccessor_partition>`, the id of the last accessor encountered is prioritized. It is often unknown, though, which accessor is the last one, so it's always better to avoid repeated ids. 
At the end, this method returns a :ref:`Dictionary <Dictionary>` with all the data obtained from the :ref:`LokStorageAccessor <LokStorageAccessor>`s. It's structure is the following:
.. codeblock::  


   {
     "partition_1_id": {
       "accessor_1_id": {
         "version": <String> (optional),
         ...
       },
       "accessor_n_id": { ... }
     },
     "partition_n_id": { ... }
   }



.. _LokGlobalStorageManager_distribute_result:

:ref:`void <void>` distribute_result\(:ref:`Dictionary <Dictionary>` result, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``\)
-----------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`distribute_result <distribute_result>` method is the central point where the result of loadings is distributed to all :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>`. 
If the ``included_accessors`` parameter is not empty, this method only distributes data to the :ref:`LokStorageAccessor <LokStorageAccessor>`s present in that :ref:`Array <Array>`. 
The version of the :ref:`LokStorageAccessor <LokStorageAccessor>`s that receives the data is determined by the ``"version"`` key of its data in the ``data`` subdictionary of the ``result`` :ref:`Dictionary <Dictionary>`. 
If there's no such entry, the version that receives the data is the latest available. 
If there are more than one :ref:`LokStorageAccessor <LokStorageAccessor>`s with the same id found, the data with that id is distributed to all of these :ref:`LokStorageAccessor <LokStorageAccessor>`s. 
The ``result`` :ref:`Dictionary <Dictionary>` that this method expects should match the following pattern:
.. codeblock::  


   {
     "result": <@GlobalScope.Error>,
     "data": {
       "accessor_1_id": {
         "version": <String>,
         ...
       },
       "accessor_n_id": { ... }
     }
   }



.. _LokGlobalStorageManager_get_saved_files_ids:

:ref:`String <String>`[] get_saved_files_ids\(\)
------------------------------------------------

The :ref:`get_saved_files_ids <get_saved_files_ids>` method returns an :ref:`Array <Array>` of :ref:`String <String>`s with the ids of all files saved in the :ref:`saves_directory <saves_directory>`.


.. _LokGlobalStorageManager_save_data:

:ref:`Dictionary <Dictionary>` save_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`bool <bool>` replace = ``false``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`save_data <save_data>` method is the main method for saving data using the :ref:`LockerPlugin <LockerPlugin>`. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.save_data <LokStorageManager_save_data>` description. 
Note that if a ``file_id`` is passed but is an empty :ref:`String <String>`, the :ref:`LokStorageManager.current_file <LokStorageManager_current_file>` is prioritized over the empty one.


.. _LokGlobalStorageManager_load_data:

:ref:`Dictionary <Dictionary>` load_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`load_data <load_data>` method is the main method for loading data using the :ref:`LockerPlugin <LockerPlugin>`. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.load_data <LokStorageManager_load_data>` description. 
Note that if a ``file_id`` is passed but is an empty :ref:`String <String>`, the :ref:`LokStorageManager.current_file <LokStorageManager_current_file>` is prioritized over the empty one.


.. _LokGlobalStorageManager_read_data:

:ref:`Dictionary <Dictionary>` read_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`read_data <read_data>` method is the main method for reading data using the :ref:`LockerPlugin <LockerPlugin>`. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.read_data <LokStorageManager_read_data>` description. 
Note that if a ``file_id`` is passed but is an empty :ref:`String <String>`, the :ref:`LokStorageManager.current_file <LokStorageManager_current_file>` is prioritized over the empty one.


.. _LokGlobalStorageManager_remove_data:

:ref:`Dictionary <Dictionary>` remove_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`remove_data <remove_data>` method is the main method for removing data using the :ref:`LockerPlugin <LockerPlugin>`. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.remove_data <LokStorageManager_remove_data>` description. 
Note that if a ``file_id`` is passed but is an empty :ref:`String <String>`, the :ref:`LokStorageManager.current_file <LokStorageManager_current_file>` is prioritized over the empty one.


.. _LokGlobalStorageManager__get_accessor_ids:

:ref:`String <String>`[] _get_accessor_ids\(:ref:`LokStorageAccessor <LokStorageAccessor>`[] from_accessors\)
-------------------------------------------------------------------------------------------------------------

The :ref:`_get_accessor_ids <_get_accessor_ids>` method returns an :ref:`Array <Array>` of :ref:`String <String>`s representing the ids from the :ref:`LokStorageAccessor <LokStorageAccessor>`s received in the ``from_accessors`` parameter.


.. _LokGlobalStorageManager__get_file_name:

:ref:`String <String>` _get_file_name\(:ref:`String <String>` file_id\)
-----------------------------------------------------------------------

The :ref:`_get_file_name <_get_file_name>` method returns a :ref:`String <String>` with the name of a file that has ``file_id`` as its id. 
If ``file_id`` is an empty :ref:`String <String>`, the file name defaults to the :ref:`save_files_prefix <save_files_prefix>`. 
If that property is an empty :ref:`String <String>`, then the file name equals to the ``file_id``. 
If both are not empty :ref:`String <String>`, then the file name equals to a nicely concatenated ``<save_files_prefix>_<file_id>``.


.. _LokGlobalStorageManager__get_file_path:

:ref:`String <String>` _get_file_path\(:ref:`String <String>` file_id\)
-----------------------------------------------------------------------

The :ref:`_get_file_path <_get_file_path>` method returns a :ref:`String <String>` with the path of a file that has ``file_id`` as its id. 
If both the :ref:`save_files_prefix <save_files_prefix>` and the ``file_id`` are empty :ref:`String <String>`s, then the file path will return an empty :ref:`String <String>` to avoid that the :ref:`saves_directory <saves_directory>` is used as a file.


.. _LokGlobalStorageManager__push_error_no_executor:

:ref:`void <void>` _push_error_no_executor\(\)
----------------------------------------------

The :ref:`_push_error_no_executor <_push_error_no_executor>` method pushes an error saying that no :ref:`LokAccessExecutor <LokAccessExecutor>` was found in this class.

