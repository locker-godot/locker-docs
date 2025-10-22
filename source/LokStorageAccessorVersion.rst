
.. _LokStorageAccessorVersion:

=========================
LokStorageAccessorVersion
=========================

**Inherits:** 

The :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` resource describes how data is saved and loaded from a :ref:`LokStorageAccessor <LokStorageAccessor>` in a specific version.

Description
===========

The purpose of this class is to provide different behaviors of how data is dealt with accross different versions of the game that require changes in the save files organization. 
In order to achieve that, this class should be extended so that different implementations of the :ref:`_retrieve_data <_retrieve_data>` and :ref:`_consume_data <_consume_data>` methods can be created for different versions of a :ref:`LokStorageAccessor <LokStorageAccessor>`. 

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
     - :ref:`number <LokStorageAccessorVersion_number>`
     - ``"1.0.0"``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`
     - :ref:`create <LokStorageAccessorVersion_create>`\(:ref:`String <String>` _number = ``"1.0.0"``\)* - :ref:`String <String>`[]
     - :ref:`get_version_parts <LokStorageAccessorVersion_get_version_parts>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)* - :ref:`String <String>`
     - :ref:`get_minor_version <LokStorageAccessorVersion_get_minor_version>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)* - :ref:`String <String>`
     - :ref:`get_patch_version <LokStorageAccessorVersion_get_patch_version>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)* - :ref:`String <String>`
     - :ref:`get_major_version <LokStorageAccessorVersion_get_major_version>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)* - :ref:`int <int>`
     - :ref:`compare_versions <LokStorageAccessorVersion_compare_versions>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)* - :ref:`int <int>`
     - :ref:`compare_minor_versions <LokStorageAccessorVersion_compare_minor_versions>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)* - :ref:`int <int>`
     - :ref:`compare_patch_versions <LokStorageAccessorVersion_compare_patch_versions>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)* - :ref:`int <int>`
     - :ref:`compare_major_versions <LokStorageAccessorVersion_compare_major_versions>`\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_retrieve_data <LokStorageAccessorVersion__retrieve_data>`\(:ref:`Dictionary <Dictionary>` _dependencies\)* - :ref:`void <void>`
     - :ref:`_consume_data <LokStorageAccessorVersion__consume_data>`\(:ref:`Dictionary <Dictionary>` _data, :ref:`Dictionary <Dictionary>` _dependencies\)




Property Descriptions
=====================


.. _LokStorageAccessorVersion_number:

:ref:`String <String>` number = ``"1.0.0"``
-------------------------------------------

The :ref:`number <number>` property specifies what version of :ref:`LokStorageAccessor <LokStorageAccessor>` this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` corresponds to. 
Initially this is set to ``"1.0.0"``, which is the default version. 
If you don't intend to version your save data, you can always just leave this as default.



Method Descriptions
===================


.. _LokStorageAccessorVersion_create:

:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` create\(:ref:`String <String>` _number = ``"1.0.0"``\)
-------------------------------------------------------------------------------------------------------------------

The :ref:`create <create>` method is a utility to create a new :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` with its properties already set to the desired values.


.. _LokStorageAccessorVersion_get_version_parts:

:ref:`String <String>`[] get_version_parts\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)
------------------------------------------------------------------------------------------------------------------

The :ref:`get_version_parts <get_version_parts>` method returns an :ref:`Array <Array>` with the substrings separated by ``"."`` that compose the :ref:`number <number>` of this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`.


.. _LokStorageAccessorVersion_get_minor_version:

:ref:`String <String>` get_minor_version\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)
----------------------------------------------------------------------------------------------------------------

The :ref:`get_minor_version <get_minor_version>` method returns a :ref:`String <String>` with the minor version in the :ref:`number <number>` of this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`.


.. _LokStorageAccessorVersion_get_patch_version:

:ref:`String <String>` get_patch_version\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)
----------------------------------------------------------------------------------------------------------------

The :ref:`get_patch_version <get_patch_version>` method returns a :ref:`String <String>` with the patch version in the :ref:`number <number>` of this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`.


.. _LokStorageAccessorVersion_get_major_version:

:ref:`String <String>` get_major_version\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version\)
----------------------------------------------------------------------------------------------------------------

The :ref:`get_major_version <get_major_version>` method returns a :ref:`String <String>` with the major version in the :ref:`number <number>` of this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`.


.. _LokStorageAccessorVersion_compare_versions:

:ref:`int <int>` compare_versions\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`compare_versions <compare_versions>` method returns an ``int`` representing if two :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s are less than (``-1``), equal (``0``) or greater than (``1``) one another.


.. _LokStorageAccessorVersion_compare_minor_versions:

:ref:`int <int>` compare_minor_versions\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`compare_minor_versions <compare_minor_versions>` method returns an ``int`` representing if the minor versions of two :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s are less than (``-1``), equal (``0``) or greater than (``1``) one another.


.. _LokStorageAccessorVersion_compare_patch_versions:

:ref:`int <int>` compare_patch_versions\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`compare_patch_versions <compare_patch_versions>` method returns an ``int`` representing if the patch versions of two :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s are less than (``-1``), equal (``0``) or greater than (``1``) one another.


.. _LokStorageAccessorVersion_compare_major_versions:

:ref:`int <int>` compare_major_versions\(:ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version1, :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` version2\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`compare_major_versions <compare_major_versions>` method returns an ``int`` representing if the major versions of two :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s are less than (``-1``), equal (``0``) or greater than (``1``) one another.


.. _LokStorageAccessorVersion__retrieve_data:

:ref:`Dictionary <Dictionary>` _retrieve_data\(:ref:`Dictionary <Dictionary>` _dependencies\)
---------------------------------------------------------------------------------------------

The :ref:`_retrieve_data <_retrieve_data>` method should be overriden by concrete implementations of :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s in order to define what data this :ref:`LokStorageAccessor <LokStorageAccessor>` should store. 
This method receives a ``dependencies`` :ref:`Dictionary <Dictionary>` that brings all information from the :ref:`LokStorageAccessor.dependency_paths <LokStorageAccessor_dependency_paths>`, so that this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` can access it. 
Any :ref:`NodePath <NodePath>`s from the :ref:`LokStorageAccessor.dependency_paths <LokStorageAccessor_dependency_paths>`'s values are converted to nodes before being passed to this method so that they can be easily referenced by this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`. 
When finished processing, this method should return a :ref:`Dictionary <Dictionary>` with the data that should be stored in a save file. 
If you're using the :ref:`LokJSONAccessStrategy <LokJSONAccessStrategy>` or the :ref:`LokEncryptedAccessStrategy <LokEncryptedAccessStrategy>` (the built-in strategies of the :ref:`LockerPlugin <LockerPlugin>`), the returned :ref:`Dictionary <Dictionary>` should only store basic data types like :ref:`String <String>`s, ``floats`` and ``bools``, so you need to make sure to transform your data accordingly. 
For parsing from complex data types like :ref:`Vector2 <Vector2>`s to :ref:`String <String>`s, I recommend using the :ref:`@GlobalScope.var_to_str <@GlobalScope_var_to_str>` method.


.. _LokStorageAccessorVersion__consume_data:

:ref:`void <void>` _consume_data\(:ref:`Dictionary <Dictionary>` _data, :ref:`Dictionary <Dictionary>` _dependencies\)
----------------------------------------------------------------------------------------------------------------------

The :ref:`_consume_data <_consume_data>` method should be overriden by concrete implementations of :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`s in order to define what happens to the ``data`` it receives when the game is loaded. 
This method receives a ``dependencies`` :ref:`Dictionary <Dictionary>` that brings all information from the :ref:`LokStorageAccessor.dependency_paths <LokStorageAccessor_dependency_paths>`, so that this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>` can access it. 
Any :ref:`NodePath <NodePath>`s from the :ref:`LokStorageAccessor.dependency_paths <LokStorageAccessor_dependency_paths>`'s values are converted to nodes before being passed to this method so that they can be easily referenced by this :ref:`LokStorageAccessorVersion <LokStorageAccessorVersion>`. 
If you're using the :ref:`LokJSONAccessStrategy <LokJSONAccessStrategy>` or the :ref:`LokEncryptedAccessStrategy <LokEncryptedAccessStrategy>` (the built-in strategies of the :ref:`LockerPlugin <LockerPlugin>`), the ``data`` :ref:`Dictionary <Dictionary>` will only be capable of storing basic data types like :ref:`String <String>`s, ``floats`` and ``bools``, so you need to make sure to transform your data accordingly. 
For parsing from :ref:`String <String>` to complex data types like :ref:`Vector2 <Vector2>`s, I recommend using the :ref:`@GlobalScope.str_to_var <@GlobalScope_str_to_var>` method.

