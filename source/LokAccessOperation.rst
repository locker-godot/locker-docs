
.. _LokAccessOperation:

==================
LokAccessOperation
==================

**Inherits:** 

The :ref:`LokAccessOperation <LokAccessOperation>` class executes given operations to access data.

Description
===========

The :ref:`LokAccessOperation <LokAccessOperation>` class helps with the execution of operations that can manipulate stored data. 
This class is used by the :ref:`LokAccessExecutor <LokAccessExecutor>` class in order to organize and queue different operations in a parallel :ref:`Thread <Thread>`. 
Since this class is used with different :ref:`Thread <Thread>`s, it uses the :ref:`Object.call_deferred <Object_call_deferred>` method when emitting signals, so that the main :ref:`Thread <Thread>` can seamlessly connect with these signals. 

**Version**: 1.0.0 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`Callable <Callable>`
     - :ref:`_callable <LokAccessOperation__callable>`
     - ````
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`Dictionary <Dictionary>`
     - :ref:`operate <LokAccessOperation_operate>`\(\)



Signal Descriptions
===================


.. _LokAccessOperation_started:

started\(\)
-----------

The :ref:`started <started>` signal is emitted when this operation starts with its :ref:`operate <operate>` method being called.


.. _LokAccessOperation_finished:

finished\(:ref:`Dictionary <Dictionary>` result\)
-------------------------------------------------

The :ref:`finished <finished>` signal is emitted when this operations finishes with the end of its :ref:`operate <operate>` method execution. 
This signal passes a ``result`` :ref:`Dictionary <Dictionary>` with the result of this operation.



Property Descriptions
=====================


.. _LokAccessOperation__callable:

:ref:`Callable <Callable>` _callable
------------------------------------

The :ref:`_callable <_callable>` property of this :ref:`LokAccessOperation <LokAccessOperation>` represents a :ref:`Callable <Callable>` that is executed in order for this :ref:`LokAccessOperation <LokAccessOperation>` to execute. 
This :ref:`Callable <Callable>` is supposed to return a :ref:`Dictionary <Dictionary>` with the result of this :ref:`LokAccessOperation <LokAccessOperation>`.



Method Descriptions
===================


.. _LokAccessOperation_operate:

:ref:`Dictionary <Dictionary>` operate\(\)
------------------------------------------

The :ref:`operate <operate>` is the main point of execution of this :ref:`LokAccessOperation <LokAccessOperation>`. 
It's this method that is responsible for emitting the :ref:`started <started>` and :ref:`finished <finished>` signals in the given times, which allows this :ref:`LokAccessOperation <LokAccessOperation>` to be handled asynchronously.

