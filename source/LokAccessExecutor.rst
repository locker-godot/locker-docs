
.. _LokAccessExecutor:

=================
LokAccessExecutor
=================

**Inherits:** 

The :ref:`LokAccessExecutor <LokAccessExecutor>` class separates accesses to another :ref:`Thread <Thread>`.

Description
===========

The :ref:`LokAccessExecutor <LokAccessExecutor>` class is responsible for managing and separating the execution of access methods to another :ref:`Thread <Thread>`, so that those operations don't block the main flow of the program. 

**Version**: 1.0.0 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)

Property Index
==============

.. list-table::
   :header-rows: 1

   * - Type
     - Name
     - Default value
   * - :ref:`LokAccessStrategy <LokAccessStrategy>`
     - :ref:`access_strategy <LokAccessExecutor_access_strategy>`
     - ``null``
   * - :ref:`Mutex <Mutex>`
     - :ref:`_mutex <LokAccessExecutor__mutex>`
     - ``new()``
   * - :ref:`Semaphore <Semaphore>`
     - :ref:`_semaphore <LokAccessExecutor__semaphore>`
     - ``new()``
   * - :ref:`Thread <Thread>`
     - :ref:`_thread <LokAccessExecutor__thread>`
     - ``new()``
   * - :ref:`bool <bool>`
     - :ref:`_exit_executor <LokAccessExecutor__exit_executor>`
     - ``false``
   * - :ref:`LokAccessOperation <LokAccessOperation>`[]
     - :ref:`_queued_operations <LokAccessExecutor__queued_operations>`
     - ``[]``
   * - :ref:`LokAccessOperation <LokAccessOperation>`
     - :ref:`_current_operation <LokAccessExecutor__current_operation>`
     - ``null``
   

Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`finish_execution <LokAccessExecutor_finish_execution>`\(\)* - :ref:`bool <bool>`
     - :ref:`has_queued_operations <LokAccessExecutor_has_queued_operations>`\(\)* - :ref:`bool <bool>`
     - :ref:`has_current_operation <LokAccessExecutor_has_current_operation>`\(\)* - :ref:`bool <bool>`
     - :ref:`is_busy <LokAccessExecutor_is_busy>`\(\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`request_get_file_ids <LokAccessExecutor_request_get_file_ids>`\(:ref:`String <String>` files_path\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`request_saving <LokAccessExecutor_request_saving>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`request_loading <LokAccessExecutor_request_loading>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`request_removing <LokAccessExecutor_request_removing>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`void <void>`
     - :ref:`_start_execution <LokAccessExecutor__start_execution>`\(\)* - :ref:`void <void>`
     - :ref:`_execute <LokAccessExecutor__execute>`\(\)* - :ref:`void <void>`
     - :ref:`_queue_operation <LokAccessExecutor__queue_operation>`\(:ref:`LokAccessOperation <LokAccessOperation>` operation\)* - :ref:`LokAccessOperation <LokAccessOperation>`
     - :ref:`_dequeue_operation <LokAccessExecutor__dequeue_operation>`\(\)* - :ref:`LokAccessOperation <LokAccessOperation>`
     - :ref:`_create_operation <LokAccessExecutor__create_operation>`\(:ref:`Callable <Callable>` callable\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_operate <LokAccessExecutor__operate>`\(:ref:`Callable <Callable>` operation_callable\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_get_saved_files_ids <LokAccessExecutor__get_saved_files_ids>`\(:ref:`String <String>` files_path\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_save_data <LokAccessExecutor__save_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_load_data <LokAccessExecutor__load_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`Dictionary <Dictionary>`
     - :ref:`_remove_data <LokAccessExecutor__remove_data>`\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)* - :ref:`void <void>`
     - :ref:`_push_error_no_access_strategy <LokAccessExecutor__push_error_no_access_strategy>`\(\)



Signal Descriptions
===================


.. _LokAccessExecutor_operation_started:

operation_started\(:ref:`StringName <StringName>` operation\)
-------------------------------------------------------------

The :ref:`operation_started <operation_started>` signal is emitted when an operation starts. 
The operation that started is passed along in the ``operation`` parameter.


.. _LokAccessExecutor_operation_finished:

operation_finished\(:ref:`Dictionary <Dictionary>` result, :ref:`StringName <StringName>` operation\)
-----------------------------------------------------------------------------------------------------

The :ref:`operation_finished <operation_finished>` signal is emitted when an operation finishes. 
The result of the operation and the operation itself are passed along in the ``result`` and ``operation`` parameters.



Property Descriptions
=====================


.. _LokAccessExecutor_access_strategy:

:ref:`LokAccessStrategy <LokAccessStrategy>` access_strategy = ``null``
-----------------------------------------------------------------------

The :ref:`access_strategy <access_strategy>` property stores the :ref:`LokAccessStrategy <LokAccessStrategy>` that this :ref:`LokAccessExecutor <LokAccessExecutor>` uses to manipulate data.


.. _LokAccessExecutor__mutex:

:ref:`Mutex <Mutex>` _mutex = ``new()``
---------------------------------------

The :ref:`_mutex <_mutex>` property stores a :ref:`Mutex <Mutex>` that helps controlling access to this :ref:`LokAccessExecutor <LokAccessExecutor>`'s properties by multiple :ref:`Thread <Thread>`s.


.. _LokAccessExecutor__semaphore:

:ref:`Semaphore <Semaphore>` _semaphore = ``new()``
---------------------------------------------------

The :ref:`_semaphore <_semaphore>` property stores a :ref:`Semaphore <Semaphore>` that controls the flow of the :ref:`_thread <_thread>` of this :ref:`LokAccessExecutor <LokAccessExecutor>`.


.. _LokAccessExecutor__thread:

:ref:`Thread <Thread>` _thread = ``new()``
------------------------------------------

The :ref:`_thread <_thread>` property stores a :ref:`Thread <Thread>` that executes all the heavy operation codes that this :ref:`LokAccessExecutor <LokAccessExecutor>` must execute.


.. _LokAccessExecutor__exit_executor:

:ref:`bool <bool>` _exit_executor = ``false``
---------------------------------------------

The :ref:`_exit_executor <_exit_executor>` property stores a ``bool`` indicating if the execution of the :ref:`_thread <_thread>` should stop.


.. _LokAccessExecutor__queued_operations:

:ref:`LokAccessOperation <LokAccessOperation>`[] _queued_operations = ``[]``
----------------------------------------------------------------------------

The :ref:`_queued_operations <_queued_operations>` property stores an :ref:`Array <Array>` of :ref:`LokAccessOperation <LokAccessOperation>`s that are queued to be executed when this :ref:`LokAccessExecutor <LokAccessExecutor>` becomes free to execute them.


.. _LokAccessExecutor__current_operation:

:ref:`LokAccessOperation <LokAccessOperation>` _current_operation = ``null``
----------------------------------------------------------------------------

The :ref:`_current_operation <_current_operation>` property stores the current :ref:`LokAccessOperation <LokAccessOperation>` that is being executed by this :ref:`LokAccessExecutor <LokAccessExecutor>`.



Method Descriptions
===================


.. _LokAccessExecutor_finish_execution:

:ref:`void <void>` finish_execution\(\)
---------------------------------------

The :ref:`finish_execution <finish_execution>` method finishes the execution of this :ref:`LokAccessExecutor <LokAccessExecutor>`'s :ref:`_thread <_thread>` by setting the :ref:`_exit_executor <_exit_executor>` property to ``false`` and awaiting the :ref:`_thread <_thread>` finish.


.. _LokAccessExecutor_has_queued_operations:

:ref:`bool <bool>` has_queued_operations\(\)
--------------------------------------------

The :ref:`has_queued_operations <has_queued_operations>` method returns a ``bool`` indicating if the :ref:`_queued_operations <_queued_operations>` has any operations queued.


.. _LokAccessExecutor_has_current_operation:

:ref:`bool <bool>` has_current_operation\(\)
--------------------------------------------

The :ref:`has_current_operation <has_current_operation>` method returns a ``bool`` indicating if the :ref:`_current_operation <_current_operation>` has an operation.


.. _LokAccessExecutor_is_busy:

:ref:`bool <bool>` is_busy\(\)
------------------------------

The :ref:`has_current_operation <has_current_operation>` method returns a ``bool`` indicating if this :ref:`LokAccessExecutor <LokAccessExecutor>` is currently busy with a :ref:`_current_operation <_current_operation>` or will be busy with one of the :ref:`_queued_operations <_queued_operations>`.


.. _LokAccessExecutor_request_get_file_ids:

:ref:`Dictionary <Dictionary>` request_get_file_ids\(:ref:`String <String>` files_path\)
----------------------------------------------------------------------------------------

The :ref:`request_get_file_ids <request_get_file_ids>` method queues an operation of getting the saved files' ids to be executed by this :ref:`LokAccessExecutor <LokAccessExecutor>` the sooner the possible. 
The parameters of this method and its return are the same of the :ref:`LokAccessStrategy.get_saved_files_ids <LokAccessStrategy_get_saved_files_ids>`, with the exception that this method is asynchronous.


.. _LokAccessExecutor_request_saving:

:ref:`Dictionary <Dictionary>` request_saving\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`request_saving <request_saving>` method queues a saving operation to be executed by this :ref:`LokAccessExecutor <LokAccessExecutor>` the sooner the possible. 
The parameters of this method and its return are the same of the :ref:`LokAccessStrategy.save_data <LokAccessStrategy_save_data>`, with the exception that this method is asynchronous.


.. _LokAccessExecutor_request_loading:

:ref:`Dictionary <Dictionary>` request_loading\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`request_loading <request_loading>` method queues a loading operation to be executed by this :ref:`LokAccessExecutor <LokAccessExecutor>` the sooner the possible. 
The parameters of this method and its return are the same of the :ref:`LokAccessStrategy.load_data <LokAccessStrategy_load_data>`, with the exception that this method is asynchronous.


.. _LokAccessExecutor_request_removing:

:ref:`Dictionary <Dictionary>` request_removing\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`request_removing <request_removing>` method queues a reading operation to be executed by this :ref:`LokAccessExecutor <LokAccessExecutor>` the sooner the possible. 
The parameters of this method and its return are the same of the :ref:`LokAccessStrategy.remove_data <LokAccessStrategy_remove_data>`, with the exception that this method is asynchronous.


.. _LokAccessExecutor__start_execution:

:ref:`void <void>` _start_execution\(\)
---------------------------------------

The :ref:`_start_execution <_start_execution>` method starts the execution of this :ref:`LokAccessExecutor <LokAccessExecutor>`'s :ref:`_thread <_thread>` with the :ref:`_execute <_execute>` method.


.. _LokAccessExecutor__execute:

:ref:`void <void>` _execute\(\)
-------------------------------

The :ref:`_execute <_execute>` method is responsible for executing the :ref:`LokAccessOperation <LokAccessOperation>`s ordered to this :ref:`LokAccessExecutor <LokAccessExecutor>` and always keep waiting for more, unless the :ref:`_exit_executor <_exit_executor>` is set to ``false``.


.. _LokAccessExecutor__queue_operation:

:ref:`void <void>` _queue_operation\(:ref:`LokAccessOperation <LokAccessOperation>` operation\)
-----------------------------------------------------------------------------------------------

The :ref:`_queue_operation <_queue_operation>` method takes a new :ref:`LokAccessOperation <LokAccessOperation>` and appends it to the :ref:`_queued_operations <_queued_operations>` property, so that this ``operation`` can be executed the sooner possible.


.. _LokAccessExecutor__dequeue_operation:

:ref:`LokAccessOperation <LokAccessOperation>` _dequeue_operation\(\)
---------------------------------------------------------------------

The :ref:`_dequeue_operation <_dequeue_operation>` method removes a :ref:`LokAccessOperation <LokAccessOperation>` from the :ref:`_queued_operations <_queued_operations>` property and returns it, so that it can be used for execution.


.. _LokAccessExecutor__create_operation:

:ref:`LokAccessOperation <LokAccessOperation>` _create_operation\(:ref:`Callable <Callable>` callable\)
-------------------------------------------------------------------------------------------------------

The :ref:`_create_operation <_create_operation>` method creates a new :ref:`LokAccessOperation <LokAccessOperation>` and returns it, making sure to connect its signals to the :ref:`operation_started <operation_started>` and :ref:`operation_finished <operation_finished>` signals.


.. _LokAccessExecutor__operate:

:ref:`Dictionary <Dictionary>` _operate\(:ref:`Callable <Callable>` operation_callable\)
----------------------------------------------------------------------------------------

The :ref:`_operate <_operate>` method receives an ``operation_callable`` and creates a new :ref:`LokAccessOperation <LokAccessOperation>`, which is appended to the :ref:`_queued_operations <_queued_operations>`, so that the :ref:`_thread <_thread>` can execute it in the :ref:`_execute <_execute>` method. 
This method then, returns the result of the operation when it is ready by awaiting the :ref:`LokAccessOperation.finished <LokAccessOperation_finished>` signal.


.. _LokAccessExecutor__get_saved_files_ids:

:ref:`Dictionary <Dictionary>` _get_saved_files_ids\(:ref:`String <String>` files_path\)
----------------------------------------------------------------------------------------

The :ref:`_get_saved_files_ids <_get_saved_files_ids>` method is responsible for using the :ref:`access_strategy <access_strategy>` to get the file ids of the saved files. 
This method is wrapped by the :ref:`request_get_file_ids <request_get_file_ids>` method, so that it can be executed asynchronously. 
If you want more information about its parameters and return, see the :ref:`LokAccessStrategy.get_saved_files_ids <LokAccessStrategy_get_saved_files_ids>` method, which has the same signature.


.. _LokAccessExecutor__save_data:

:ref:`Dictionary <Dictionary>` _save_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`Dictionary <Dictionary>` data, :ref:`bool <bool>` replace = ``false``\)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_save_data <_save_data>` method is responsible for using the :ref:`access_strategy <access_strategy>` to save data. 
This method is wrapped by the :ref:`request_saving <request_saving>` method, so that it can be executed asynchronously. 
If you want more information about its parameters and return, see the :ref:`LokAccessStrategy.save_data <LokAccessStrategy_save_data>` method, which has the same signature.


.. _LokAccessExecutor__load_data:

:ref:`Dictionary <Dictionary>` _load_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_load_data <_load_data>` method is responsible for using the :ref:`access_strategy <access_strategy>` to load data. 
This method is wrapped by the :ref:`request_loading <request_loading>` method, so that it can be executed asynchronously. 
If you want more information about its parameters and return, see the :ref:`LokAccessStrategy.load_data <LokAccessStrategy_load_data>` method, which has the same signature.


.. _LokAccessExecutor__remove_data:

:ref:`Dictionary <Dictionary>` _remove_data\(:ref:`String <String>` file_path, :ref:`String <String>` file_format, :ref:`String <String>`[] partition_ids = ``[]``, :ref:`String <String>`[] accessor_ids = ``[]``, :ref:`String <String>`[] version_numbers = ``[]``\)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`_remove_data <_remove_data>` method is responsible for using the :ref:`access_strategy <access_strategy>` to remove data. 
This method is wrapped by the :ref:`request_removing <request_removing>` method, so that it can be executed asynchronously. 
If you want more information about its parameters and return, see the :ref:`LokAccessStrategy.remove_data <LokAccessStrategy_remove_data>` method, which has the same signature.


.. _LokAccessExecutor__push_error_no_access_strategy:

:ref:`void <void>` _push_error_no_access_strategy\(\)
-----------------------------------------------------

The :ref:`_push_error_no_access_strategy <_push_error_no_access_strategy>` method pushes an error warning that no :ref:`LokAccessStrategy <LokAccessStrategy>`s are set in this :ref:`LokAccessExecutor <LokAccessExecutor>`.

