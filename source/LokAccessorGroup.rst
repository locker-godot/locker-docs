
.. _LokAccessorGroup:

================
LokAccessorGroup
================

**Inherits:** 

The :ref:`LokAccessorGroup <LokAccessorGroup>` represents a collection of :ref:`LokStorageAccessor <LokStorageAccessor>`s.

Description
===========

This class is the uppermost in the :ref:`LokStorageManager <LokStorageManager>` hierarchy since it represents a general collection of :ref:`LokStorageAccessor <LokStorageAccessor>`s. 
Besides being able to group :ref:`accessors <accessors>` together, this class allows performing group operations, which trigger each :ref:`accessors <accessors>` operations one after the other, and emits handy signals to know when the group operations started and finished. 
This is useful when it's wanted to perform multiple operations on different save files, which can be indicated individually by each :ref:`LokStorageAccessor <LokStorageAccessor>`. 

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
     - :ref:`current_version <LokAccessorGroup_current_version>`
     - ``""``
   * - :ref:`LokStorageAccessor <LokStorageAccessor>`[]
     - :ref:`accessors <LokAccessorGroup_accessors>`
     - ``[]``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`bool <bool>`
     - :ref:`add_accessor <LokAccessorGroup_add_accessor>`\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor\)* - :ref:`bool <bool>`
     - :ref:`remove_accessor <LokAccessorGroup_remove_accessor>`\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor\)* - :ref:`void <void>`
     - :ref:`save_accessor_group <LokAccessorGroup_save_accessor_group>`\(:ref:`String <String>` version_number = ``current_version``\)* - :ref:`void <void>`
     - :ref:`load_accessor_group <LokAccessorGroup_load_accessor_group>`\(\)* - :ref:`void <void>`
     - :ref:`remove_accessor_group <LokAccessorGroup_remove_accessor_group>`\(\)



Signal Descriptions
===================


.. _LokAccessorGroup_group_saving_started:

group_saving_started\(\)
------------------------

The :ref:`group_saving_started <group_saving_started>` signal is emitted when a group of save operations was started by this :ref:`LokAccessorGroup <LokAccessorGroup>`.


.. _LokAccessorGroup_group_loading_started:

group_loading_started\(\)
-------------------------

The :ref:`group_loading_started <group_loading_started>` signal is emitted when a group of load operations was started by this :ref:`LokAccessorGroup <LokAccessorGroup>`.


.. _LokAccessorGroup_group_removing_started:

group_removing_started\(\)
--------------------------

The :ref:`group_removing_started <group_removing_started>` signal is emitted when a group of remove operations was started by this :ref:`LokAccessorGroup <LokAccessorGroup>`.


.. _LokAccessorGroup_group_saving_finished:

group_saving_finished\(\)
-------------------------

The :ref:`group_saving_finished <group_saving_finished>` signal is emitted when a group of save operations was finished by this :ref:`LokAccessorGroup <LokAccessorGroup>`.


.. _LokAccessorGroup_group_loading_finished:

group_loading_finished\(\)
--------------------------

The :ref:`group_loading_finished <group_loading_finished>` signal is emitted when a group of load operations was finished by this :ref:`LokAccessorGroup <LokAccessorGroup>`.


.. _LokAccessorGroup_group_removing_finished:

group_removing_finished\(\)
---------------------------

The :ref:`group_removing_finished <group_removing_finished>` signal is emitted when a group of remove operations was finished by this :ref:`LokAccessorGroup <LokAccessorGroup>`.



Property Descriptions
=====================


.. _LokAccessorGroup_current_version:

:ref:`String <String>` current_version = ``""``
-----------------------------------------------

The :ref:`current_version <current_version>` property is used as the version with which data is saved when using this :ref:`LokAccessorGroup <LokAccessorGroup>`. 
By default, it is set to an empty :ref:`String <String>`, which is converted to the latest available version.


.. _LokAccessorGroup_accessors:

:ref:`LokStorageAccessor <LokStorageAccessor>`[] accessors = ``[]``
-------------------------------------------------------------------

The :ref:`accessors <accessors>` property is an :ref:`Array <Array>` responsible for storing all the :ref:`LokStorageAccessor <LokStorageAccessor>`s interesting to this :ref:`LokAccessorGroup <LokAccessorGroup>`.



Method Descriptions
===================


.. _LokAccessorGroup_add_accessor:

:ref:`bool <bool>` add_accessor\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor\)
------------------------------------------------------------------------------------------

The :ref:`add_accessor <add_accessor>` method is responsible for adding a new :ref:`LokStorageAccessor <LokStorageAccessor>` to the :ref:`accessors <accessors>` list, so that it can have its data manipulated together with the other ones.


.. _LokAccessorGroup_remove_accessor:

:ref:`bool <bool>` remove_accessor\(:ref:`LokStorageAccessor <LokStorageAccessor>` accessor\)
---------------------------------------------------------------------------------------------

The :ref:`remove_accessor <remove_accessor>` method is responsible for removing a :ref:`LokStorageAccessor <LokStorageAccessor>` from the :ref:`accessors <accessors>` list, so that it doesn't have its data manipulated by this :ref:`LokAccessorGroup <LokAccessorGroup>` anymore.


.. _LokAccessorGroup_save_accessor_group:

:ref:`void <void>` save_accessor_group\(:ref:`String <String>` version_number = ``current_version``\)
-----------------------------------------------------------------------------------------------------

The :ref:`save_accessor_group <save_accessor_group>` method is responsible for performing one save operation for each of the :ref:`accessors <accessors>` in this :ref:`LokAccessorGroup <LokAccessorGroup>`. 
The start and finish of this group of operations is notified via the :ref:`group_saving_started <group_saving_started>` and :ref:`group_saving_finished <group_saving_finished>` signals. 
If it's wanted, a ``version_number`` can be passed to dictate what version to use in this operation. In case none is provided, the :ref:`current_version <current_version>` is used.


.. _LokAccessorGroup_load_accessor_group:

:ref:`void <void>` load_accessor_group\(\)
------------------------------------------

The :ref:`load_accessor_group <load_accessor_group>` method is responsible for performing one load operation for each of the :ref:`accessors <accessors>` in this :ref:`LokAccessorGroup <LokAccessorGroup>`. 
The start and finish of this group of operations is notified via the :ref:`group_loading_started <group_loading_started>` and :ref:`group_loading_finished <group_loading_finished>` signals.


.. _LokAccessorGroup_remove_accessor_group:

:ref:`void <void>` remove_accessor_group\(\)
--------------------------------------------

The :ref:`remove_accessor_group <remove_accessor_group>` method is responsible for performing one remove operation for each of the :ref:`accessors <accessors>` in this :ref:`LokAccessorGroup <LokAccessorGroup>`. 
The start and finish of this group of operations is notified via the :ref:`group_removing_started <group_removing_started>` and :ref:`group_removing_finished <group_removing_finished>` signals.

