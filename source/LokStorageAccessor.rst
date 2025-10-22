
.. _LokStorageAccessor:

==================
LokStorageAccessor
==================

**Inherits:** 

The :ref:`LokStorageAccessor <LokStorageAccessor>` is a node specialized in saving, loading and removing data.

Description
===========

This class uses different :ref:`versions <versions>` to handle data saving and loading accross different game versions. 
In order to do the job of managing the data it receives, this class must have at least one :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` set in its :ref:`versions <versions>` and point to it through the :ref:`version_number <version_number>` property. 
Such version should define the logic of how the data is gathered to be saved and how it is used when loaded. 
See more about it here :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`. 

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
     - :ref:`id <LokStorageAccessor_id>`
     - ``""``
   * - :ref:`String <String>`
     - :ref:`file <LokStorageAccessor_file>`
     - ``""``
   * - :ref:`String <String>`
     - :ref:`partition <LokStorageAccessor_partition>`
     - ``""``
   * - :ref:`String <String>`
     - :ref:`version_number <LokStorageAccessor_version_number>`
     - ``"1.0.0"``
   * - :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`[]
     - :ref:`versions <LokStorageAccessor_versions>`
     - ``[]``
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`dependency_paths <LokStorageAccessor_dependency_paths>`
     - ``{}``
   * - :ref:`bool <bool>`
     - :ref:`active <LokStorageAccessor_active>`
     - ``true``
   * - :ref:`LokStorageManager <LokStorageManager>`
     - :ref:`_storage_manager <LokStorageAccessor__storage_manager>`
     - ``LokGlobalStorageManager``
   * - :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`
     - :ref:`_version <LokStorageAccessor__version>`
     - ````
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`LokStorageAccessor <LokStorageAccessor>`
     - :ref:`create <LokStorageAccessor_create>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`[] _versions, :ref:`String <String>` _version_number\)* - :ref:`bool <bool>`
     - :ref:`select_version <LokStorageAccessor_select_version>`\(:ref:`String <String>` number\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`save_data <LokStorageAccessor_save_data>`\(:ref:`String <String>` file_id = ``file``, :ref:`String <String>` version_number = ``""``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`load_data <LokStorageAccessor_load_data>`\(:ref:`String <String>` file_id = ``file``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`remove_data <LokStorageAccessor_remove_data>`\(:ref:`String <String>` file_id = ``file``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`retrieve_data <LokStorageAccessor_retrieve_data>`\(\)* - :ref:`void <void>`
     - :ref:`consume_data <LokStorageAccessor_consume_data>`\(:ref:`Dictionary <Dictionary>` data\)* - :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`
     - :ref:`_find_version <LokStorageAccessor__find_version>`\(:ref:`String <String>` number\)* - :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`
     - :ref:`_find_latest_version <LokStorageAccessor__find_latest_version>`\(\)* - :ref:`void <void>`
     - :ref:`_update_version <LokStorageAccessor__update_version>`\(\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_get_dependencies <LokStorageAccessor__get_dependencies>`\(\)* - :ref:`String <String>`
     - :ref:`_get_readable_name <LokStorageAccessor__get_readable_name>`\(\)* - :ref:`void <void>`
     - :ref:`_push_error_no_manager <LokStorageAccessor__push_error_no_manager>`\(\)* - :ref:`void <void>`
     - :ref:`_push_error_unactive_accessor <LokStorageAccessor__push_error_unactive_accessor>`\(\)



Signal Descriptions
===================


.. _LokStorageAccessor_saving_started:

saving_started\(\)
------------------

The :ref:`saving_started <saving_started>` is emitted when a save operation was started by this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor_loading_started:

loading_started\(\)
-------------------

The :ref:`loading_started <loading_started>` is emitted when a load operation was started by this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor_removing_started:

removing_started\(\)
--------------------

The :ref:`removing_started <removing_started>` is emitted when a remove operation was started by this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor_saving_finished:

saving_finished\(:ref:`Dictionary <Dictionary>` result\)
--------------------------------------------------------

The :ref:`saving_finished <saving_finished>` is emitted when a save operation was finished by this :ref:`LokStorageAccessor <LokStorageAccessor>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data saved.


.. _LokStorageAccessor_loading_finished:

loading_finished\(:ref:`Dictionary <Dictionary>` result\)
---------------------------------------------------------

The :ref:`loading_finished <loading_finished>` is emitted when a load operation was finished by this :ref:`LokStorageAccessor <LokStorageAccessor>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code and a ``"data"`` key, with the data loaded.


.. _LokStorageAccessor_removing_finished:

removing_finished\(:ref:`Dictionary <Dictionary>` result\)
----------------------------------------------------------

The :ref:`removing_finished <removing_finished>` is emitted when a remove operation was finished by this :ref:`LokStorageAccessor <LokStorageAccessor>`. 
This signal brings a :ref:`Dictionary <Dictionary>` representing the result of the operation. This :ref:`Dictionary <Dictionary>` has a ``"status"`` key, with a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code; a ``"data"`` key, with the data removed; and a ``"updated_data"`` key, with the data that wasn't removed.



Property Descriptions
=====================


.. _LokStorageAccessor_id:

:ref:`String <String>` id = ``""``
----------------------------------

The :ref:`id <id>` property specifies what is the unique id of this :ref:`LokStorageAccessor <LokStorageAccessor>`. 
You should always plan your save system to make sure your :ref:`LokStorageAccessor <LokStorageAccessor>`'s ids don't crash when saving data. 
If they do, there may arise data inconsistency issues or even loss of data. 
Multiple :ref:`LokStorageAccessor <LokStorageAccessor>`s with same :ref:`id <id>` is fine, though, with the :ref:`load_data <load_data>` operation, or in the case those :ref:`LokStorageAccessor <LokStorageAccessor>`s belong to different save files.


.. _LokStorageAccessor_file:

:ref:`String <String>` file = ``""``
------------------------------------

The :ref:`file <file>` property specifies from what file the data of this :ref:`LokStorageAccessor <LokStorageAccessor>` belongs to. 
If left empty, it is considered as being the default file. 
This :ref:`file <file>` property is only used by the operations of this :ref:`LokStorageAccessor <LokStorageAccessor>` as the default file, not in general operations that include multiple :ref:`LokStorageAccessor <LokStorageAccessor>`s. 
This is useful when in need of implementing something like a file selection screen.


.. _LokStorageAccessor_partition:

:ref:`String <String>` partition = ``""``
-----------------------------------------

The :ref:`partition <partition>` property specifies in what partition the data of this :ref:`LokStorageAccessor <LokStorageAccessor>` should be stored. 
If left empty, it means it is stored in the default partition. 
The separation in partitions is useful when a :ref:`LokStorageAccessor <LokStorageAccessor>` or group of :ref:`LokStorageAccessor <LokStorageAccessor>`s have data that has to be loaded often by itself, like the data from a player that needs to be loaded whenever it logs in the game.


.. _LokStorageAccessor_version_number:

:ref:`String <String>` version_number = ``"1.0.0"``
---------------------------------------------------

The :ref:`version_number <version_number>` property stores a :ref:`String <String>` that points to one of the :ref:`versions <versions>`' :ref:`LokStorageAccessorVersion.number <LokStorageAccessorVersion_number>`. 
To work properly, this :ref:`LokStorageAccessor <LokStorageAccessor>` needs to point to a version number existent in the :ref:`versions <versions>` list, which is already done by default if the list has at least one :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` that hadn't had its :ref:`LokStorageAccessorVersion.number <LokStorageAccessorVersion_number>` altered.


.. _LokStorageAccessor_versions:

:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`[] versions = ``[]``
--------------------------------------------------------------------------------

The :ref:`versions <versions>` property stores a list of :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s with which this :ref:`LokStorageAccessor <LokStorageAccessor>` is able to save and load data. 
Different versions can be useful if the game needs to change its data organization accross different versions, with the addition of features, for example. 
To actually do something, this :ref:`LokStorageAccessor <LokStorageAccessor>` needs at least one :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` to save and load data. 
In order for this :ref:`LokStorageAccessor <LokStorageAccessor>` to correctly find new versions, they should be added to this :ref:`Array <Array>` through a new :ref:`Array <Array>`, so that this property's setter gets triggered. Alternatively, you can use a method like :ref:`Array.append <Array_append>`, but make sure to call the :ref:`_update_version <_update_version>` method next.


.. _LokStorageAccessor_dependency_paths:

:ref:`Dictionary <Dictionary>` dependency_paths = ``{}``
--------------------------------------------------------

The :ref:`dependency_paths <dependency_paths>` property stores a :ref:`Dictionary <Dictionary>` that helps with keeping track of dependencies that this :ref:`LokStorageAccessor <LokStorageAccessor>` needs to get or send data to. 
This property stores keys and values that are sent to the active :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` so that it can manipulate the data accordingly. 
If the keys are :ref:`NodePath <NodePath>`s, before being sent to a :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`, the :ref:`NodePath <NodePath>`s are converted into :ref:`Node <Node>`s, so that the :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` can have their references, despite it being a :ref:`Resource <Resource>`.


.. _LokStorageAccessor_active:

:ref:`bool <bool>` active = ``true``
------------------------------------

The :ref:`active <active>` property is a flag that tells whether this :ref:`LokStorageAccessor <LokStorageAccessor>` should operate its data when its :ref:`save_data <save_data>`, :ref:`load_data <load_data>` or :ref:`remove_data <remove_data>` methods try to. 
By default it is set to ``true`` so that this :ref:`LokStorageAccessor <LokStorageAccessor>` can do its tasks as expected.


.. _LokStorageAccessor__storage_manager:

:ref:`LokStorageManager <LokStorageManager>` _storage_manager = ``LokGlobalStorageManager``
-------------------------------------------------------------------------------------------

The :ref:`_storage_manager <_storage_manager>` property is just a reference to the :ref:`LokGlobalStorageManager <LokGlobalStorageManager>` autoload. 
Its reference is stored in this property so it can be more easily mocked in unit tests. 
The value of this property shouldn't be altered. Doing so may cause the saving and loading system to not work properly.


.. _LokStorageAccessor__version:

:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` _version
---------------------------------------------------------------------

The :ref:`_version <_version>` property stores the current :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` selected by the :ref:`version_number <version_number>`. 
This is the :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` that's used when saving and loading data through this :ref:`LokStorageAccessor <LokStorageAccessor>`.



Method Descriptions
===================


.. _LokStorageAccessor_create:

:ref:`LokStorageAccessor <LokStorageAccessor>` create\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`[] _versions, :ref:`String <String>` _version_number\)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`create <create>` method is a utility to create a new :ref:`LokStorageAccessor <LokStorageAccessor>` with its properties already set to the desired values.


.. _LokStorageAccessor_select_version:

:ref:`bool <bool>` select_version\(:ref:`String <String>` number\)
------------------------------------------------------------------

The :ref:`select_version <select_version>` method looks through all the :ref:`versions <versions>` and sets the current :ref:`_version <_version>` to be the one with number matching the ``number`` parameter. 
If no such version is found, ``false`` is returned and the :ref:`_version <_version>` is set to ``null``, else ``true`` is returned.


.. _LokStorageAccessor_save_data:

:ref:`Dictionary <Dictionary>` save_data\(:ref:`String <String>` file_id = ``file``, :ref:`String <String>` version_number = ``""``\)
-------------------------------------------------------------------------------------------------------------------------------------

The :ref:`save_data <save_data>` method uses the :ref:`LokStorageManager <LokStorageManager>` to save the data of this :ref:`LokStorageAccessor <LokStorageAccessor>`. 
By default, the version used is the ``latest``, but that can be defined in the ``version_number`` parameter.


.. _LokStorageAccessor_load_data:

:ref:`Dictionary <Dictionary>` load_data\(:ref:`String <String>` file_id = ``file``\)
-------------------------------------------------------------------------------------

The :ref:`load_data <load_data>` method uses the :ref:`LokStorageManager <LokStorageManager>` to load the data of this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor_remove_data:

:ref:`Dictionary <Dictionary>` remove_data\(:ref:`String <String>` file_id = ``file``\)
---------------------------------------------------------------------------------------

The :ref:`remove_data <remove_data>` method uses the :ref:`LokStorageManager <LokStorageManager>` to remove the data of this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor_retrieve_data:

:ref:`Dictionary <Dictionary>` retrieve_data\(\)
------------------------------------------------

The :ref:`retrieve_data <retrieve_data>` method uses the :ref:`LokStorageAccessorVersion._retrieve_data <LokStorageAccessorVersion__retrieve_data>` to collect the data that should be saved by the :ref:`LokStorageAccessor.save_data <LokStorageAccessor_save_data>` method.


.. _LokStorageAccessor_consume_data:

:ref:`void <void>` consume_data\(:ref:`Dictionary <Dictionary>` data\)
----------------------------------------------------------------------

The :ref:`consume_data <consume_data>` method uses the :ref:`LokStorageAccessorVersion._consume_data <LokStorageAccessorVersion__consume_data>` to use the data that was loaded by the :ref:`LokStorageAccessor.load_data <LokStorageAccessor_load_data>` method.


.. _LokStorageAccessor__find_version:

:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` _find_version\(:ref:`String <String>` number\)
-----------------------------------------------------------------------------------------------------------

The :ref:`_find_version <_find_version>` method looks through all the :ref:`versions <versions>` and returns the one that has same :ref:`LokStorageAccessorVersion.number <LokStorageAccessorVersion_number>` as the passed in the ``number`` parameter. 
If no such version is found, ``null`` is returned.


.. _LokStorageAccessor__find_latest_version:

:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` _find_latest_version\(\)
-------------------------------------------------------------------------------------

The :ref:`_find_latest_version <_find_latest_version>` method looks through all the :ref:`versions <versions>` and returns the one that has the latest :ref:`LokStorageAccessorVersion.number <LokStorageAccessorVersion_number>`. 
If no such version is found, ``null`` is returned.


.. _LokStorageAccessor__update_version:

:ref:`void <void>` _update_version\(\)
--------------------------------------

The :ref:`_update_version <_update_version>` method serves to make the :ref:`_version <_version>` property properly store the current version that the :ref:`version_number <version_number>` points to.


.. _LokStorageAccessor__get_dependencies:

:ref:`Dictionary <Dictionary>` _get_dependencies\(\)
----------------------------------------------------

The :ref:`_get_dependencies <_get_dependencies>` method returns a copy of the :ref:`dependency_paths <dependency_paths>` :ref:`Dictionary <Dictionary>`, but with :ref:`Node <Node>`s as values, instead of the original :ref:`NodePath <NodePath>`s. 
This is useful when passing their reference to the :ref:`LokStorageAccessorVersion._retrieve_data <LokStorageAccessorVersion__retrieve_data>` and :ref:`LokStorageAccessorVersion._consume_data <LokStorageAccessorVersion__consume_data>` methods.


.. _LokStorageAccessor__get_readable_name:

:ref:`String <String>` _get_readable_name\(\)
---------------------------------------------

The :ref:`_get_readable_name <_get_readable_name>` method is a way of getting a more user friendly name for this :ref:`LokStorageAccessor <LokStorageAccessor>`, for use in debugging.


.. _LokStorageAccessor__push_error_no_manager:

:ref:`void <void>` _push_error_no_manager\(\)
---------------------------------------------

The :ref:`_push_error_no_manager <_push_error_no_manager>` method pushes an error warning that there's no :ref:`_storage_manager <_storage_manager>` set in this :ref:`LokStorageAccessor <LokStorageAccessor>`.


.. _LokStorageAccessor__push_error_unactive_accessor:

:ref:`void <void>` _push_error_unactive_accessor\(\)
----------------------------------------------------

The :ref:`_push_error_unactive_accessor <_push_error_unactive_accessor>` method pushes an error warning that an operation was tried in an unactive :ref:`LokStorageAccessor <LokStorageAccessor>`.

