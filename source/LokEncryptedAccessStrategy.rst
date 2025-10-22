
.. _LokEncryptedAccessStrategy:

==========================
LokEncryptedAccessStrategy
==========================

**Inherits:** 

The :ref:`LokEncryptedAccessStrategy <LokEncryptedAccessStrategy>` class is responsible for implementing encrypted data accessing.

Description
===========

This class inherits from the :ref:`LokAccessStrategy <LokAccessStrategy>` in order to implement its :ref:`_save_partition <_save_partition>` and :ref:`_load_partition <_load_partition>` methods and with that provide saving and loading functionalities for encrypted data. 

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
     - :ref:`password <LokEncryptedAccessStrategy_password>`
     - ````
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`_save_partition <LokEncryptedAccessStrategy__save_partition>`\(:ref:`String <String>` partition_path, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_load_partition <LokEncryptedAccessStrategy__load_partition>`\(:ref:`String <String>` partition_path\)




Property Descriptions
=====================


.. _LokEncryptedAccessStrategy_password:

:ref:`String <String>` password
-------------------------------

The :ref:`password <password>` property is used when encrypting/ decrypting data, so it must be set to a password intended before starting using this class.



Method Descriptions
===================


.. _LokEncryptedAccessStrategy__save_partition:

:ref:`Dictionary <Dictionary>` _save_partition\(:ref:`String <String>` partition_path, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_save_partition <_save_partition>` method overrides its super counterpart :ref:`LokAccessStrategy._save_partition <LokAccessStrategy__save_partition>` in order to provide ``data`` saving in a encrypted format. 
When finished, this method returns a :ref:`Dictionary <Dictionary>` with the data it saved. 
To read more about the parameters of this method, see :ref:`LokAccessStrategy._save_partition <LokAccessStrategy__save_partition>`.


.. _LokEncryptedAccessStrategy__load_partition:

:ref:`Dictionary <Dictionary>` _load_partition\(:ref:`String <String>` partition_path\)
---------------------------------------------------------------------------------------

The :ref:`_load_partition <_load_partition>` method overrides its super counterpart :ref:`LokAccessStrategy._load_partition <LokAccessStrategy__load_partition>` in order to provide encrypted data loading. 
When finished, this method returns a :ref:`Dictionary <Dictionary>` with the data it loaded. 
To read more about the parameters of this method and the format of its return, see :ref:`LokAccessStrategy._load_partition <LokAccessStrategy__load_partition>`.

