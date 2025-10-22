
.. _LokStorageManager:

=================
LokStorageManager
=================

**Inherits:** 

The :ref:`LokStorageManager <LokStorageManager>` is the super class of the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` and :ref:`LokSceneStorageManager <LokSceneStorageManager>` classes.

Description
===========

This super class serves as an interface for the :ref:`save_data <save_data>`, :ref:`load_data <load_data>`, :ref:`read_data <read_data>` and :ref:`remove_data <remove_data>` methods, so that its sub classes can override them. 

**Version**: 1.0.0
**Author**: github.com/nadjiel <github.com/nadjiel>_

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`String <String>`
     - :ref:`current_file <LokStorageManager_current_file>`
     - ``""``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`save_data <LokStorageManager_save_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`load_data <LokStorageManager_load_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`read_data <LokStorageManager_read_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`remove_data <LokStorageManager_remove_data>`\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`String <String>`
     - :ref:`_get_readable_name <LokStorageManager__get_readable_name>`\(\)



Signal Descriptions
===================


.. _LokStorageManager_saving_started:

saving_started\(\)
------------------

The :ref:`saving_started <saving_started>` signal is emitted when a save operation was started by this :ref:`LokStorageManager <LokStorageManager>`.


.. _LokStorageManager_loading_started:

loading_started\(\)
-------------------

The :ref:`loading_started <loading_started>` signal is emitted when a load operation was started by this :ref:`LokStorageManager <LokStorageManager>`.


.. _LokStorageManager_reading_started:

reading_started\(\)
-------------------

The :ref:`reading_started <reading_started>` signal is emitted when a read operation was started by this :ref:`LokStorageManager <LokStorageManager>`.


.. _LokStorageManager_removing_started:

removing_started\(\)
--------------------

The :ref:`removing_started <removing_started>` signal is emitted when a remove operation was started by this :ref:`LokStorageManager <LokStorageManager>`.


.. _LokStorageManager_saving_finished:

saving_finished\(:ref:`Dictionary <Dictionary>` result\)
--------------------------------------------------------

The :ref:`saving_finished <saving_finished>` signal is emitted when a save operation was finished by this :ref:`LokStorageManager <LokStorageManager>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data saved.


.. _LokStorageManager_loading_finished:

loading_finished\(:ref:`Dictionary <Dictionary>` result\)
---------------------------------------------------------

The :ref:`loading_finished <loading_finished>` signal is emitted when a load operation was finished by this :ref:`LokStorageManager <LokStorageManager>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data loaded.


.. _LokStorageManager_reading_finished:

reading_finished\(:ref:`Dictionary <Dictionary>` result\)
---------------------------------------------------------

The :ref:`reading_finished <reading_finished>` signal is emitted when a read operation was finished by this :ref:`LokStorageManager <LokStorageManager>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data readed.


.. _LokStorageManager_removing_finished:

removing_finished\(:ref:`Dictionary <Dictionary>` result\)
----------------------------------------------------------

The :ref:`removing_finished <removing_finished>` signal is emitted when a remove operation was finished by this :ref:`LokStorageManager <LokStorageManager>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data removed.



Property Descriptions
=====================


.. _LokStorageManager_current_file:

:ref:`String <String>` current_file = ``""``
--------------------------------------------

The :ref:`current_file <current_file>` property stores the id of the default file to be used when performing operations with this :ref:`LokStorageManager <LokStorageManager>`.



Method Descriptions
===================


.. _LokStorageManager_save_data:

:ref:`Dictionary <Dictionary>` save_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`String <String>` version_number = ``current_version``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`bool <bool>` replace = ``false``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`save_data <save_data>` method should save the information from all active :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokStorageManager <LokStorageManager>` in a desired file. 
This method receives several parameters to customize that process. 
The ``file_id`` should determine in what file the game should be saved. This id defaults to the one set in the :ref:`current_file <current_file>` property. 
The ``version_number`` parameter is supposed to specify what version of the registered :ref:`LokStorageAccessor <LokStorageAccessor>`s should be used to save the game. By default, it is set to the :ref:`LokAccessorGroup.current_version <LokAccessorGroup_current_version>`, which converts to the latest version available. 
The ``included_accessors`` parameter is an :ref:`Array <Array>` that represents what is the subset of :ref:`LokStorageAccessor <LokStorageAccessor>`s that should be involved in this saving process. If left empty, as default, it would mean that all :ref:`LokStorageAccessor <LokStorageAccessor>`s currently registered would have their informations saved. 
The ``replace`` parameter is a flag that tells whether the previous data saved, if any, should be overwritten by the new one. It's not recommended setting this flag to ``true`` since :ref:`LokStorageAccessor <LokStorageAccessor>`s not included in the saving may need that overwritten data later on. This flag should only be used if you know the previous data and are sure you want to delete it. 
At the end, this method should return the result of the saving via a :ref:`Dictionary <Dictionary>` with a ``"status"`` key specifying a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code, and a ``"data"`` key storing all data saved. 
The start and finish of this operation should be notified via the :ref:`saving_started <saving_started>` and :ref:`saving_finished <saving_finished>` signals.


.. _LokStorageManager_load_data:

:ref:`Dictionary <Dictionary>` load_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`load_data <load_data>` method should load the information from all active :ref:`LokAccessorGroup.accessors <LokAccessorGroup_accessors>` of this :ref:`LokStorageManager <LokStorageManager>` from a desired file and further distribute it to them, so they can use it with their :ref:`LokStorageAccessor.consume_data <LokStorageAccessor_consume_data>` method. 
This method receives several parameters to customize that process. 
The ``file_id`` should determine from what file the game should be loaded. This id defaults to the one set in the :ref:`current_file <current_file>` property. 
Besides that, the ``included_accessors`` parameter is an :ref:`Array <Array>` that represents what is the subset of :ref:`LokStorageAccessor <LokStorageAccessor>`s that should be involved in this loading process. If left empty, as default, it would mean that all :ref:`LokStorageAccessor <LokStorageAccessor>`s currently registered would have their informations loaded. 
To provide yet more control over what data is loaded, the ``partition_ids`` and ``version_numbers`` parameters can be passed, serving to filter what information should be applied to the game. 
If you have sure about in what partitions is the data you want to load, passing their ``partition_ids`` is more efficient since the loading only needs to check those partitions. 
If the optional parameters are left empty, as default, it means that all ``included_accessors``, ``partition_ids`` and ``version_numbers`` are used when loading. 
At the end, this method should return the result of the loading via a :ref:`Dictionary <Dictionary>` with a ``"status"`` key specifying a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code, and a ``"data"`` key storing all data loaded. 
The start and finish of this operation should be notified via the :ref:`loading_started <loading_started>` and :ref:`loading_finished <loading_finished>` signals.


.. _LokStorageManager_read_data:

:ref:`Dictionary <Dictionary>` read_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`read_data <read_data>` method should read the information from a desired file, like the :ref:`load_data <load_data>` method, but not distribute that data to its respective :ref:`LokStorageAccessor <LokStorageAccessor>`s. 
Excluding that small difference, this method is basically the same as the :ref:`load_data <load_data>` method, but more inclined for possibilitating saved data analysis without necessarily applying it to the game. 
To read more about the parameters and return of this method, see the :ref:`load_data <load_data>` method. 
The start and finish of this operation should be notified via the :ref:`reading_started <reading_started>` and :ref:`reading_finished <reading_finished>` signals.


.. _LokStorageManager_remove_data:

:ref:`Dictionary <Dictionary>` remove_data\(:ref:`String <String>` file_id = ``current_file``, :ref:`LokStorageAccessor <LokStorageAccessor>`[] included_accessors = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`remove_data <remove_data>` method should remove the information from a desired file of specified by the ``file_id`` parameter. 
By default, that ``file_id`` is set to the :ref:`current_file <current_file>` property. 
The ``included_accessors``, ``partition_ids`` and ``version_numbers`` parameters can be used to filter what should be removed, if it's not desired to remove the entire file. 
To read more about those parameters, see the :ref:`load_data <load_data>` method, which uses them as filters in the same way. 
At the end, this method should return the result of the removing via a :ref:`Dictionary <Dictionary>` with a ``"status"`` key specifying a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code, a ``"data"`` key storing all data removed, and an ``"updated_data"`` key storing all data kept. 
The start and finish of this operation should be notified via the :ref:`removing_started <removing_started>` and :ref:`removing_finished <removing_finished>` signals.


.. _LokStorageManager__get_readable_name:

:ref:`String <String>` _get_readable_name\(\)
---------------------------------------------

The :ref:`_get_readable_name <_get_readable_name>` method is a utility for debugging. 
It returns a more user friendly name for this node, so that errors can use it to be clearer.

