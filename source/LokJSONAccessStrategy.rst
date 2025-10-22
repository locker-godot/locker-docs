
.. _LokJSONAccessStrategy:

=====================
LokJSONAccessStrategy
=====================

**Inherits:** 

The :ref:`LokJSONAccessStrategy <LokJSONAccessStrategy>` class is responsible for implementing ``JSON`` data accessing.

Description
===========

This class inherits from the :ref:`LokAccessStrategy <LokAccessStrategy>` in order to implement its :ref:`_save_partition <_save_partition>` and :ref:`_load_partition <_load_partition>` methods and, with that, provide saving and loading functionalities for ``JSON`` data. 

**Version**: 1.0.0
**Author**: github.com/nadjiel <github.com/nadjiel>_


Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`_save_partition <LokJSONAccessStrategy__save_partition>`\(:ref:`String <String>` partition_path, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_load_partition <LokJSONAccessStrategy__load_partition>`\(:ref:`String <String>` partition_path\)





Method Descriptions
===================


.. _LokJSONAccessStrategy__save_partition:

:ref:`Dictionary <Dictionary>` _save_partition\(:ref:`String <String>` partition_path, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_save_partition <_save_partition>` method overrides its super counterpart :ref:`LokAccessStrategy._save_partition <LokAccessStrategy__save_partition>` in order to provide ``data`` saving in the ``JSON`` format. 
When finished, this method returns a :ref:`Dictionary <Dictionary>` with the data it saved. 
To read more about the parameters of this method, see :ref:`LokAccessStrategy._save_partition <LokAccessStrategy__save_partition>`.


.. _LokJSONAccessStrategy__load_partition:

:ref:`Dictionary <Dictionary>` _load_partition\(:ref:`String <String>` partition_path\)
---------------------------------------------------------------------------------------

The :ref:`_load_partition <_load_partition>` method overrides its super counterpart :ref:`LokAccessStrategy._load_partition <LokAccessStrategy__load_partition>` in order to provide data loading in the ``JSON`` format. 
When finished, this method returns a :ref:`Dictionary <Dictionary>` with the data it loaded. 
To read more about the parameters of this method and the format of its return, see :ref:`LokAccessStrategy._load_partition <LokAccessStrategy__load_partition>`.

