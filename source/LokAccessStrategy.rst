
.. _LokAccessStrategy:

=================
LokAccessStrategy
=================

**Inherits:** 

The :ref:`LokAccessStrategy <LokAccessStrategy>` super class is responsible for defining how the writing and reading from files should be performed.

Description
===========

This class should have its :ref:`_save_partition <_save_partition>` and :ref:`_load_partition <_load_partition>` methods overriden in order to provide concrete implementations for the saving and loading functionalities. 
The :ref:`LokJSONAccessStrategy <LokJSONAccessStrategy>` and :ref:`LokEncryptedAccessStrategy <LokEncryptedAccessStrategy>` classes are two strategies built-in to the :ref:`LockerPlugin <LockerPlugin>`, but if you want, you can define your own access strategies inheriting from the :ref:`LokAccessStrategy <LokAccessStrategy>` class. 
If you need to deal with the file system when inheriting this class, the :ref:`LokFileSystemUtil <LokFileSystemUtil>` class provides lots of static methods that help with decreasing the boilerplate code needed for that. 

**Version**: 1.0.0
**Author**: github.com/nadjiel <github.com/nadjiel>_


Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`create_result <LokAccessStrategy_create_result>`\(:ref:`Dictionary <Dictionary>` data = ``{}``, :ref:`int <int>` status = ``0``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`get_saved_files_ids <LokAccessStrategy_get_saved_files_ids>`\(:ref:`String <String>` files_path\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`save_data <LokAccessStrategy_save_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`load_data <LokAccessStrategy_load_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`remove_data <LokAccessStrategy_remove_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`String <String>`
     - :ref:`_get_partition_name <LokAccessStrategy__get_partition_name>`\(:ref:`String <String>` file_path, :ref:`String <String>` partition_id, :ref:`String <String>` file_format\)* - :ref:`String <String>`[]
     - :ref:`_get_partitions <LokAccessStrategy__get_partitions>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] wanted_ids = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_filter_data <LokAccessStrategy__filter_data>`\(:ref:`Dictionary <Dictionary>` data, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_append_partition_to_data <LokAccessStrategy__append_partition_to_data>`\(:ref:`Dictionary <Dictionary>` data, :ref:`String <String>` partition_id\)* - :ref:`String <String>`
     - :ref:`_get_file_id <LokAccessStrategy__get_file_id>`\(:ref:`String <String>` file_name\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_remove_partition <LokAccessStrategy__remove_partition>`\(:ref:`String <String>` partition_path, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_save_partition <LokAccessStrategy__save_partition>`\(:ref:`String <String>` _partition_path, :ref:`Dictionary <Dictionary>` _data, :ref:`bool <bool>` _replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_load_partition <LokAccessStrategy__load_partition>`\(:ref:`String <String>` _partition_path\)





Method Descriptions
===================


.. _LokAccessStrategy_create_result:

:ref:`Dictionary <Dictionary>` create_result\(:ref:`Dictionary <Dictionary>` data = ``{}``, :ref:`int <int>` status = ``0``\)
-----------------------------------------------------------------------------------------------------------------------------

The :ref:`create_result <create_result>` method helps with the creation of a :ref:`Dictionary <Dictionary>` representing the result of an operation done by this :ref:`LokAccessStrategy <LokAccessStrategy>`. 
The returned :ref:`Dictionary <Dictionary>` has two keys: the ``"status"``, which stores a :ref:`@GlobalScope.Error <@GlobalScope_Error>` code, and the ``"data"``, which stores a :ref:`Dictionary <Dictionary>` with the resultant data of an operation.


.. _LokAccessStrategy_get_saved_files_ids:

:ref:`Dictionary <Dictionary>` get_saved_files_ids\(:ref:`String <String>` files_path\)
---------------------------------------------------------------------------------------

The :ref:`get_saved_files_ids <get_saved_files_ids>` method returns a result :ref:`Dictionary <Dictionary>` (with the same structure of the one created by the :ref:`create_result <create_result>`) whose ``"data"`` field stores an :ref:`Array <Array>` of :ref:`String <String>`s with the ids of all files saved in the ``files_path``.


.. _LokAccessStrategy_save_data:

:ref:`Dictionary <Dictionary>` save_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`save_data <save_data>` method uses the :ref:`_save_partition <_save_partition>` to save the information provided through the ``data`` :ref:`Dictionary <Dictionary>` in their respective partitions. 
The ``file_path`` parameter should specify the path to the folder where the data is to be saved and the ``file_format`` specifies what's the format of the files that compose the data saved (such format shouldn't include the ``"."``). 
Optionally, the ``replace`` parameter can be passed to tell if the data should override any already existent data. 
The structure that the ``data`` :ref:`Dictionary <Dictionary>` should have is as follows:
.. codeblock::  


   {
     "partition_id_1": {
       "accessor_id_1": {
         ...
         "version": <String> (optional)
       },
       "accessor_id_n": { ... },
     },
     "partition_id_n": { ... }
   }


The return of this method is a :ref:`Dictionary <Dictionary>` with a ``"status"`` field representing the status of the operation and a ``"data"`` field with the data that was saved. That :ref:`Dictionary <Dictionary>` follows the same structure as the one in returned by the :ref:`load_data <load_data>` method.


.. _LokAccessStrategy_load_data:

:ref:`Dictionary <Dictionary>` load_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`load_data <load_data>` method uses the :ref:`_load_partition <_load_partition>` method to load the information from the save directory in the ``file_path``. 
The ``file_format`` parameter specifies from what file format the data should be read (such format shouldn't include the ``"."``). 
Optionally, a ``partition_ids`` parameter can be passed to specify from what partitions the data should be loaded. 
Also, ``accessor_ids`` and ``version_numbers`` can be passed to filter even more what information to bring back. 
If left as default, that means all partitions, accessors, and versions are read, which corresponds to all data from the save file. 
After completing the loading, this method returns a :ref:`Dictionary <Dictionary>` containing all data obtained. Its format is as follows:
.. codeblock::  


   {
     "status": <@GlobalScope.Error>,
     "data": {
       "accessor_id_1": {
         ...
         "version": <String> (optional),
         "partition": <String>
       },
       "accessor_id_n": { ... }
     }
   }

If an error occurs, the corresponding :ref:`@GlobalScope.Error <@GlobalScope_Error>` code is returned in the ``"status"`` field of the :ref:`Dictionary <Dictionary>`.


.. _LokAccessStrategy_remove_data:

:ref:`Dictionary <Dictionary>` remove_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`remove_data <remove_data>` method uses the :ref:`_remove_partition <_remove_partition>` method to remove the save directory in the ``file_path``, or some of its data. 
The ``file_format`` parameter specifies from what file format the data should be removed (such format shouldn't include the ``"."``). 
Optionally, a ``partition_ids`` parameter can be passed to specify from what partitions the data should be removed. 
Also, ``accessor_ids`` and ``version_numbers`` can be passed to filter even more what information to remove. 
If left as default, that means all partitions, accessors, and versions are removed, which corresponds to all data from the save file. 
After completing the removal, this method returns a :ref:`Dictionary <Dictionary>` containing all data obtained. That :ref:`Dictionary <Dictionary>` brings the removed data in the ``"data"`` field and the data the wasn't removed stays in the ``"updated_data"`` field. The format of the returned :ref:`Dictionary <Dictionary>` is shown in more details below:
.. codeblock::  


   {
     "status": <@GlobalScope.Error>,
     "data": {
       "accessor_id_1": {
         ...
         "version": <String> (optional),
         "partition": <String>
       },
       "accessor_id_n": { ... }
     },
     "updated_data": { ... }
   }

If an error occurs, the corresponding :ref:`@GlobalScope.Error <@GlobalScope_Error>` code is returned in the ``"status"`` field of the :ref:`Dictionary <Dictionary>`.


.. _LokAccessStrategy__get_partition_name:

:ref:`String <String>` _get_partition_name\(:ref:`String <String>` file_path, :ref:`String <String>` partition_id, :ref:`String <String>` file_format\)
-------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_get_partition_name <_get_partition_name>` method receives a ``file_path``, a ``partition_id`` and a ``file_format``, all of which are :ref:`String <String>`s, and returns another :ref:`String <String>` representing the name of the partition represented by those data. 
The partition name here refers to the file name of the partition with the format suffix. 
**Example:**
.. codeblock::  


   var partition_name: String = _get_partition_name(
     "res://saves/file_1", "partition_1", "sav"
   )
   # This would return "partition_1.sav"

In the case the ``partition_id`` is an empty :ref:`String <String>`, this method considers it as being a partition with the same name as its file, so in the previous example, if the ``partition_id`` was ``""``, the result would be ``"file_1.sav"``.


.. _LokAccessStrategy__get_partitions:

:ref:`String <String>`[] _get_partitions\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] wanted_ids = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_get_partitions <_get_partitions>` method searches the names of the partitions in a given ``file_path`` with a specific ``file_format``. 
Only the partitions with id specified in the ``wanted_ids`` are brought in the result. If that parameter in empty, though, all partitions found are returned.


.. _LokAccessStrategy__filter_data:

:ref:`Dictionary <Dictionary>` _filter_data\(:ref:`Dictionary <Dictionary>` data, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_filter_data <_filter_data>` method receives a ``data`` :ref:`Dictionary <Dictionary>` other parameters that serve as filters for which entries of that :ref:`Dictionary <Dictionary>` should be kept. 
The filter parameters are the ``accessor_ids``, ``partition_ids`` and the ``version_numbers``. All of these are :ref:`Array <Array>` of :ref:`String <String>`s that identify the entries of the ``data`` that should be kept in the :ref:`Dictionary <Dictionary>` returned by this method. 
To work properly, this method expects that the ``data`` parameter follows the structure:
.. codeblock::  


   {
     "accessor_id_1": {
       ...
       "partition": <String>,
       "version": <String> (optional)
     },
     "accessor_id_n": { ... }
   }



.. _LokAccessStrategy__append_partition_to_data:

:ref:`Dictionary <Dictionary>` _append_partition_to_data\(:ref:`Dictionary <Dictionary>` data, :ref:`String <String>` partition_id\)
------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_append_partition_to_data <_append_partition_to_data>` method receives a ``data`` :ref:`Dictionary <Dictionary>` and a ``partition_id`` :ref:`String <String>`. The ``data`` parameter must be a :ref:`Dictionary <Dictionary>` with other :ref:`Dictionary <Dictionary>`s as its values, so that this method can set that ``partition_id`` as the value of a ``"partition"`` key in each of those sub dictionaries.


.. _LokAccessStrategy__get_file_id:

:ref:`String <String>` _get_file_id\(:ref:`String <String>` file_name\)
-----------------------------------------------------------------------

The :ref:`_get_file_id <_get_file_id>` method returns a :ref:`String <String>` with the id of a file that has ``file_name`` as its name. 
If the file has no ``"_"``, its entire name is its id, else, its id is considered to be the part after the first ``"_"``.


.. _LokAccessStrategy__remove_partition:

:ref:`Dictionary <Dictionary>` _remove_partition\(:ref:`String <String>` partition_path, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_remove_partition <_remove_partition>` method removes data from the partition specified by the ``partition_path`` parameter. 
At the end, this method returns a :ref:`Dictionary <Dictionary>` with the data obtained. The format of that :ref:`Dictionary <Dictionary>` follows the same structure as the one returned by the :ref:`remove_data <remove_data>` method.


.. _LokAccessStrategy__save_partition:

:ref:`Dictionary <Dictionary>` _save_partition\(:ref:`String <String>` _partition_path, :ref:`Dictionary <Dictionary>` _data, :ref:`bool <bool>` _replace = ``false``\)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_save_partition <_save_partition>` method should be overwritten so that it saves ``data`` in the partition specified by the ``partition_path`` parameter. 
Optionally, the ``replace`` parameter can be passed to tell if the data should override any already existent data. 
The format of the ``data`` :ref:`Dictionary <Dictionary>` should follow the structure below:
.. codeblock::  


   {
     "accessor_id_1": {
       ...
       "version": <String> (optional)
     },
     "accessor_id_n": { ... },
   }



.. _LokAccessStrategy__load_partition:

:ref:`Dictionary <Dictionary>` _load_partition\(:ref:`String <String>` _partition_path\)
----------------------------------------------------------------------------------------

The :ref:`_load_partition <_load_partition>` method should be overwritten so that it loads data from the partition specified by the ``partition_path`` parameter. 
At the end, this method should return a :ref:`Dictionary <Dictionary>` with the data obtained. The format of that :ref:`Dictionary <Dictionary>` should follow the same structure as the one returned by the :ref:`load_data <load_data>` method.

