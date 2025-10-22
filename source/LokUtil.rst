
.. _LokUtil:

=======
LokUtil
=======

**Inherits:** 

The :ref:`LokUtil <LokUtil>` class is a utility class that brings random useful static methods that can be used wherever convenient.

Description
===========

The purpose of this class is helping with common repetitive code that is needed in multiple places. 
Since the methods of this class are ``static`` it doesn't need to be instantiated. 

**Version**: 1.0.0 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)


Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`bool <bool>`
     - :ref:`filter_value <LokUtil_filter_value>`\(:ref:`Array <Array>` filter, :ref:`Variant <Variant>` value\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`filter_dictionary <LokUtil_filter_dictionary>`\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` filter\)* - :ref:`Dictionary <Dictionary>`[]
     - :ref:`split_dictionary <LokUtil_split_dictionary>`\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` spliter\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`map_dictionary <LokUtil_map_dictionary>`\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` mapper\)* - :ref:`bool <bool>`
     - :ref:`check_and_disconnect_signal <LokUtil_check_and_disconnect_signal>`\(:ref:`Object <Object>` object, :ref:`StringName <StringName>` signal_name, :ref:`Callable <Callable>` callable\)* - :ref:`void <void>`
     - :ref:`check_and_disconnect_signals <LokUtil_check_and_disconnect_signals>`\(:ref:`Object <Object>` object, :ref:`Dictionary <Dictionary>`[] signals\)* - :ref:`bool <bool>`
     - :ref:`check_and_connect_signal <LokUtil_check_and_connect_signal>`\(:ref:`Object <Object>` object, :ref:`StringName <StringName>` signal_name, :ref:`Callable <Callable>` callable, :ref:`int <int>` flags = ``0``\)* - :ref:`void <void>`
     - :ref:`check_and_connect_signals <LokUtil_check_and_connect_signals>`\(:ref:`Object <Object>` object, :ref:`Dictionary <Dictionary>`[] signals\)





Method Descriptions
===================


.. _LokUtil_filter_value:

:ref:`bool <bool>` filter_value\(:ref:`Array <Array>` filter, :ref:`Variant <Variant>` value\)
----------------------------------------------------------------------------------------------

The :ref:`filter_value <filter_value>` method is a helper function that takes a ``filter`` :ref:`Array <Array>` and a ``value`` to be filtered. 
This function, then, tests if the ``value`` is present in the ``filter`` :ref:`Array <Array>` (using the ``in`` operator). 
If present, ``true`` is returned to indicate the filtering passed, if absent, ``false`` is returned to indicate the filtering didn't pass. 
If the received ``filter`` is an empty :ref:`Array <Array>`, this function considers the filtering as passed.


.. _LokUtil_filter_dictionary:

:ref:`Dictionary <Dictionary>` filter_dictionary\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` filter\)
--------------------------------------------------------------------------------------------------------------------------

The :ref:`filter_dictionary <filter_dictionary>` method takes a ``dict`` (:ref:`Dictionary <Dictionary>`) and a ``filter`` :ref:`Callable <Callable>` and uses that :ref:`Callable <Callable>` to test for each key/ value pair of that ``dict`` if such entry should be kept or not in the resultant :ref:`Dictionary <Dictionary>`. 
In order to realize the tests, the ``filter`` :ref:`Callable <Callable>` should accept two values: a ``key`` and a ``value``. That :ref:`Callable <Callable>` should then return a ``bool`` indicating if that pair should be kept in the result.


.. _LokUtil_split_dictionary:

:ref:`Dictionary <Dictionary>`[] split_dictionary\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` spliter\)
----------------------------------------------------------------------------------------------------------------------------

The :ref:`split_dictionary <split_dictionary>` method works similarly to the :ref:`filter_dictionary <filter_dictionary>` method, but instead of returning only a :ref:`Dictionary <Dictionary>` with the values that passed the filtering, this method returns an :ref:`Array <Array>` with two :ref:`Dictionary <Dictionary>`s: one with the entries that passed the filtering, and the one with the entries that didn't.


.. _LokUtil_map_dictionary:

:ref:`Dictionary <Dictionary>` map_dictionary\(:ref:`Dictionary <Dictionary>` dict, :ref:`Callable <Callable>` mapper\)
-----------------------------------------------------------------------------------------------------------------------

The :ref:`map_dictionary <map_dictionary>` method takes a ``dict`` (:ref:`Dictionary <Dictionary>`) and a ``mapper`` :ref:`Callable <Callable>` and uses that :ref:`Callable <Callable>` to transform each key/ value pair of the original :ref:`Dictionary <Dictionary>` into a new value in a new :ref:`Dictionary <Dictionary>`. 
In order to realize that mapping, the ``mapper`` :ref:`Callable <Callable>` should accept two values: a ``key`` and a ``value``. That :ref:`Callable <Callable>` should then return a value that will occupy the place of the received ``value`` in the new :ref:`Dictionary <Dictionary>`.


.. _LokUtil_check_and_disconnect_signal:

:ref:`bool <bool>` check_and_disconnect_signal\(:ref:`Object <Object>` object, :ref:`StringName <StringName>` signal_name, :ref:`Callable <Callable>` callable\)
----------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`check_and_disconnect_signal <check_and_disconnect_signal>` method tries to disconnect a ``callable`` from a signal in an ``object`` if they are connected. 
If they aren't, this method returns ``false`` to indicate that nothing was done. If the ``object`` is ``null`` ``false`` is also returned, and nothing is done. 
If the disconection is successful, ``true`` is returned.


.. _LokUtil_check_and_disconnect_signals:

:ref:`void <void>` check_and_disconnect_signals\(:ref:`Object <Object>` object, :ref:`Dictionary <Dictionary>`[] signals\)
--------------------------------------------------------------------------------------------------------------------------

The :ref:`check_and_disconnect_signals <check_and_disconnect_signals>` method tries to disconnect all the callables and signals passed in the ``signals`` ``Array``. The ``signals`` parameter must be passed as an ``Array`` which elements must be in the following format: ``{ "name": <signal_name>, "callable": <callable_reference> }`` In the ``object`` parameter is ``null``, this method won't do nothing.


.. _LokUtil_check_and_connect_signal:

:ref:`bool <bool>` check_and_connect_signal\(:ref:`Object <Object>` object, :ref:`StringName <StringName>` signal_name, :ref:`Callable <Callable>` callable, :ref:`int <int>` flags = ``0``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`check_and_connect_signal <check_and_connect_signal>` method tries to connect a ``callable`` to a signal in an ``object``. 
If the ``object`` is ``null``, ``false`` is returned and nothing is done. 
If the connection is successful, ``true`` is returned.


.. _LokUtil_check_and_connect_signals:

:ref:`void <void>` check_and_connect_signals\(:ref:`Object <Object>` object, :ref:`Dictionary <Dictionary>`[] signals\)
-----------------------------------------------------------------------------------------------------------------------

The :ref:`check_and_connect_signals <check_and_connect_signals>` method tries to connect all the callables and signals passed in the ``signals`` ``Array``. The ``signals`` parameter must be passed as an ``Array`` which elements must be in the following format: ``{ "name": <signal_name>, "callable": <callable_reference>, "flags": <optional_flags> }`` If the ``object`` parameter is ``null``, this method won't do nothing.

