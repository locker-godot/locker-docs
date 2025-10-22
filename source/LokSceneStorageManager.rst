
.. _LokSceneStorageManager:

======================
LokSceneStorageManager
======================

**Inherits:** 

The :ref:`LokSceneStorageManager <LokSceneStorageManager>` class can be communicate with the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` Singleton.

Description
===========

This class is useful when it is desired to trigger the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` methods through signal emissions in the scene tree using the inspector, for example. 
Also, this class can be used to perform certain operations including only some nodes of the current scene. 

**Version**: 1.0.0
**Author**: github.com/nadjiel <github.com/nadjiel>_

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`LokStorageManager <LokStorageManager>`
     - :ref:`_global_manager <LokSceneStorageManager__global_manager>`
     - ``LokGlobalStorageManager``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`_push_error_no_manager <LokSceneStorageManager__push_error_no_manager>`\(\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`save_data <LokSceneStorageManager_save_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`load_data <LokSceneStorageManager_load_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`read_data <LokSceneStorageManager_read_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`remove_data <LokSceneStorageManager_remove_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)




Property Descriptions
=====================


.. _LokSceneStorageManager__global_manager:

:ref:`LokStorageManager <LokStorageManager>` _global_manager = ``LokGlobalStorageManager``
------------------------------------------------------------------------------------------

The :ref:`_global_manager <_global_manager>` property should not be altered since it's just a reference to the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` autoload. 
Its reference is stored here instead of called directly to make mocking it with unit testing easier.



Method Descriptions
===================


.. _LokSceneStorageManager__push_error_no_manager:

:ref:`void <void>` _push_error_no_manager\(\)
---------------------------------------------

The :ref:`_push_error_no_manager <_push_error_no_manager>` method pushes an error indicating that no :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` was found in the :ref:`_global_manager <_global_manager>` property, which shouldn't happen if that property wasn't altered, as recommended in its description.


.. _LokSceneStorageManager_save_data:

:ref:`Dictionary <Dictionary>` save_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`bool <bool>` replace = ``false``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`save_data <save_data>` method is an intermidiate to calling the :ref:`LokGlobalStorageManager.save_data <LokGlobalStorageManager_save_data>` method. 
Using this method, though, only the :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokSceneStorageManager <LokSceneStorageManager>` are included in the saving process, by default. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.save_data <LokStorageManager_save_data>` description. 
The start and finish of this operation is notified via the :ref:`LokStorageManager.saving_started <LokStorageManager_saving_started>` and :ref:`LokStorageManager.saving_finished <LokStorageManager_saving_finished>` signals.


.. _LokSceneStorageManager_load_data:

:ref:`Dictionary <Dictionary>` load_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`load_data <load_data>` method is an intermidiate to calling the :ref:`LokGlobalStorageManager.load_data <LokGlobalStorageManager_load_data>` method. 
Using this method, though, only the :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokSceneStorageManager <LokSceneStorageManager>` are included in the loading process, by default. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.load_data <LokStorageManager_load_data>` description. 
The start and finish of this operation is notified via the :ref:`LokStorageManager.loading_started <LokStorageManager_loading_started>` and :ref:`LokStorageManager.loading_finished <LokStorageManager_loading_finished>` signals.


.. _LokSceneStorageManager_read_data:

:ref:`Dictionary <Dictionary>` read_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`read_data <read_data>` method is an intermidiate to calling the :ref:`LokGlobalStorageManager.read_data <LokGlobalStorageManager_read_data>` method. 
Using this method, though, only the :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokSceneStorageManager <LokSceneStorageManager>` are included in the reading process, by default. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.read_data <LokStorageManager_read_data>` description. 
The start and finish of this operation is notified via the :ref:`LokStorageManager.reading_started <LokStorageManager_reading_started>` and :ref:`LokStorageManager.reading_finished <LokStorageManager_reading_finished>` signals.


.. _LokSceneStorageManager_remove_data:

:ref:`Dictionary <Dictionary>` remove_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``accessors``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`remove_data <remove_data>` method is an intermidiate to calling the :ref:`LokGlobalStorageManager.remove_data <LokGlobalStorageManager_remove_data>` method. 
Using this method, though, only the :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokSceneStorageManager <LokSceneStorageManager>` are included in the removing process, by default. 
To read more about the parameters and return of this method, see the :ref:`LokStorageManager.remove_data <LokStorageManager_remove_data>` description. 
The start and finish of this operation is notified via the :ref:`LokStorageManager.removing_started <LokStorageManager_removing_started>` and :ref:`LokStorageManager.removing_finished <LokStorageManager_removing_finished>` signals.

