
.. _LokFileSystemUtil:

=================
LokFileSystemUtil
=================

**Inherits:** 

The :ref:`LokFileSystemUtil <LokFileSystemUtil>` class provides utilities to deal with the file system.

Description
===========

The objective of this class is to help with boilerplate code when manipulating files or directories in the file system. 

**Version**: 1.0.0 
**Author**: Daniel Sousa (github.com/nadjiel <github.com/nadjiel>_)


Method Index
============

.. list-table::
   :header-rows: 1

   * - Return type
     - Signature
   * - :ref:`void <void>`
     - :ref:`push_error_directory_creation_failed <LokFileSystemUtil_push_error_directory_creation_failed>`\(:ref:`String <String>` path, :ref:`int <int>` error_code\)* - :ref:`void <void>`
     - :ref:`push_error_file_writing_or_creation_failed <LokFileSystemUtil_push_error_file_writing_or_creation_failed>`\(:ref:`String <String>` path, :ref:`int <int>` error_code\)* - :ref:`void <void>`
     - :ref:`push_error_directory_not_found <LokFileSystemUtil_push_error_directory_not_found>`\(:ref:`String <String>` path\)* - :ref:`void <void>`
     - :ref:`push_error_file_not_found <LokFileSystemUtil_push_error_file_not_found>`\(:ref:`String <String>` path\)* - :ref:`void <void>`
     - :ref:`push_error_file_reading_failed <LokFileSystemUtil_push_error_file_reading_failed>`\(:ref:`String <String>` path, :ref:`int <int>` error_code\)* - :ref:`void <void>`
     - :ref:`push_error_json_parse_failed <LokFileSystemUtil_push_error_json_parse_failed>`\(:ref:`JSON <JSON>` json, :ref:`int <int>` error_code\)* - :ref:`void <void>`
     - :ref:`push_error_directory_or_file_removal_failed <LokFileSystemUtil_push_error_directory_or_file_removal_failed>`\(:ref:`String <String>` path, :ref:`int <int>` error_code\)* - :ref:`int <int>`
     - :ref:`create_directory <LokFileSystemUtil_create_directory>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`create_directory_if_not_exists <LokFileSystemUtil_create_directory_if_not_exists>`\(:ref:`String <String>` path\)* - :ref:`bool <bool>`
     - :ref:`directory_exists <LokFileSystemUtil_directory_exists>`\(:ref:`String <String>` path\)* - :ref:`PackedStringArray <PackedStringArray>`
     - :ref:`get_file_names <LokFileSystemUtil_get_file_names>`\(:ref:`String <String>` path, :ref:`String <String>`[] formats = ``[]``\)* - :ref:`PackedStringArray <PackedStringArray>`
     - :ref:`get_subdirectory_names <LokFileSystemUtil_get_subdirectory_names>`\(:ref:`String <String>` path\)* - :ref:`bool <bool>`
     - :ref:`directory_is_empty <LokFileSystemUtil_directory_is_empty>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`remove_directory_or_file <LokFileSystemUtil_remove_directory_or_file>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`remove_directory_recursive <LokFileSystemUtil_remove_directory_recursive>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`remove_directory_if_exists <LokFileSystemUtil_remove_directory_if_exists>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`remove_directory_recursive_if_exists <LokFileSystemUtil_remove_directory_recursive_if_exists>`\(:ref:`String <String>` path\)* - :ref:`String <String>`
     - :ref:`get_directory_name <LokFileSystemUtil_get_directory_name>`\(:ref:`String <String>` directory_path\)* - :ref:`int <int>`
     - :ref:`write_or_create_file <LokFileSystemUtil_write_or_create_file>`\(:ref:`String <String>` path, :ref:`String <String>` content = ``""``\)* - :ref:`int <int>`
     - :ref:`write_or_create_encrypted_file <LokFileSystemUtil_write_or_create_encrypted_file>`\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`String <String>` content = ``""``\)* - :ref:`int <int>`
     - :ref:`create_file_if_not_exists <LokFileSystemUtil_create_file_if_not_exists>`\(:ref:`String <String>` path\)* - :ref:`int <int>`
     - :ref:`create_encrypted_file_if_not_exists <LokFileSystemUtil_create_encrypted_file_if_not_exists>`\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`String <String>` content = ``""``\)* - :ref:`bool <bool>`
     - :ref:`file_exists <LokFileSystemUtil_file_exists>`\(:ref:`String <String>` path\)* - :ref:`String <String>`
     - :ref:`read_file <LokFileSystemUtil_read_file>`\(:ref:`String <String>` path\)* - :ref:`String <String>`
     - :ref:`read_encrypted_file <LokFileSystemUtil_read_encrypted_file>`\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`bool <bool>` suppress_errors = ``false``\)* - :ref:`Variant <Variant>`
     - :ref:`parse_json_from_string <LokFileSystemUtil_parse_json_from_string>`\(:ref:`String <String>` string, :ref:`bool <bool>` suppress_errors\)* - :ref:`Resource <Resource>`[]
     - :ref:`load_resources <LokFileSystemUtil_load_resources>`\(:ref:`String <String>` directory_path, :ref:`String <String>` resource_type = ``""``\)* - :ref:`int <int>`
     - :ref:`remove_file_if_exists <LokFileSystemUtil_remove_file_if_exists>`\(:ref:`String <String>` path\)* - :ref:`String <String>`
     - :ref:`join_file_name <LokFileSystemUtil_join_file_name>`\(:ref:`String <String>` file_prefix, :ref:`String <String>` file_format\)* - :ref:`String <String>`
     - :ref:`get_file_name <LokFileSystemUtil_get_file_name>`\(:ref:`String <String>` file_path\)* - :ref:`String <String>`
     - :ref:`get_file_format <LokFileSystemUtil_get_file_format>`\(:ref:`String <String>` file_name\)* - :ref:`String <String>`
     - :ref:`get_file_prefix <LokFileSystemUtil_get_file_prefix>`\(:ref:`String <String>` file_name\)





Method Descriptions
===================


.. _LokFileSystemUtil_push_error_directory_creation_failed:

:ref:`void <void>` push_error_directory_creation_failed\(:ref:`String <String>` path, :ref:`int <int>` error_code\)
-------------------------------------------------------------------------------------------------------------------

The :ref:`push_error_directory_creation_failed <push_error_directory_creation_failed>` method is used to push an error when a directory creation fails. 
The ``path`` of where the creation was tried is expected in the parameters together with an ``error_code`` indicating what kind of error happened.


.. _LokFileSystemUtil_push_error_file_writing_or_creation_failed:

:ref:`void <void>` push_error_file_writing_or_creation_failed\(:ref:`String <String>` path, :ref:`int <int>` error_code\)
-------------------------------------------------------------------------------------------------------------------------

The :ref:`push_error_file_writing_or_creation_failed <push_error_file_writing_or_creation_failed>` method is used to push an error when a file creation or writing operation fails. 
The ``path`` of where the operation was tried is expected in the parameters together with an ``error_code`` indicating what kind of error happened.


.. _LokFileSystemUtil_push_error_directory_not_found:

:ref:`void <void>` push_error_directory_not_found\(:ref:`String <String>` path\)
--------------------------------------------------------------------------------

The :ref:`push_error_directory_not_found <push_error_directory_not_found>` method is used to push an error warning that the ``path`` doesn't point to an existing directory.


.. _LokFileSystemUtil_push_error_file_not_found:

:ref:`void <void>` push_error_file_not_found\(:ref:`String <String>` path\)
---------------------------------------------------------------------------

The :ref:`push_error_file_not_found <push_error_file_not_found>` method is used to push an error warning that the ``path`` doesn't point to an existing file.


.. _LokFileSystemUtil_push_error_file_reading_failed:

:ref:`void <void>` push_error_file_reading_failed\(:ref:`String <String>` path, :ref:`int <int>` error_code\)
-------------------------------------------------------------------------------------------------------------

The :ref:`push_error_file_reading_failed <push_error_file_reading_failed>` method is used to push an error when a file reading fails. 
The ``path`` of where the operation was tried is expected in the parameters together with an ``error_code`` indicating what kind of error happened.


.. _LokFileSystemUtil_push_error_json_parse_failed:

:ref:`void <void>` push_error_json_parse_failed\(:ref:`JSON <JSON>` json, :ref:`int <int>` error_code\)
-------------------------------------------------------------------------------------------------------

The :ref:`push_error_json_parse_failed <push_error_json_parse_failed>` method is used to push an error when a :ref:`JSON <JSON>` parsing fails. 
The ``json`` argument is the :ref:`JSON <JSON>` instance that failed and the ``error_code`` argument represents the :ref:`@GlobalScope.Error <@GlobalScope_Error>` that occured.


.. _LokFileSystemUtil_push_error_directory_or_file_removal_failed:

:ref:`void <void>` push_error_directory_or_file_removal_failed\(:ref:`String <String>` path, :ref:`int <int>` error_code\)
--------------------------------------------------------------------------------------------------------------------------

The :ref:`push_error_directory_or_file_removal_failed <push_error_directory_or_file_removal_failed>` method is used to push an error when a directory or file removal fails. 
The ``path`` where the removal was tried is expected in the parameters together with an ``error_code`` indicating what kind of error happened.


.. _LokFileSystemUtil_create_directory:

:ref:`int <int>` create_directory\(:ref:`String <String>` path\)
----------------------------------------------------------------

The :ref:`create_directory <create_directory>` method creates a new directory in the path specified by the ``path`` parameter. 
If an error occurs, this method pushes it, either way, this method returns an :ref:`@GlobalScope.Error <@GlobalScope_Error>` code specifying the success of the operation.


.. _LokFileSystemUtil_create_directory_if_not_exists:

:ref:`int <int>` create_directory_if_not_exists\(:ref:`String <String>` path\)
------------------------------------------------------------------------------

The :ref:`create_directory_if_not_exists <create_directory_if_not_exists>` method uses the :ref:`directory_exists <directory_exists>` and :ref:`create_directory <create_directory>` methods to create a directory only if it doesn't already exist. 
If it already exists, this method returns the ``ERR_ALREADY_EXISTS`` error.


.. _LokFileSystemUtil_directory_exists:

:ref:`bool <bool>` directory_exists\(:ref:`String <String>` path\)
------------------------------------------------------------------

The :ref:`directory_exists <directory_exists>` method checks if a directory exists in the path specified by the ``path`` parameter and returns a ``bool`` indicating the result.


.. _LokFileSystemUtil_get_file_names:

:ref:`PackedStringArray <PackedStringArray>` get_file_names\(:ref:`String <String>` path, :ref:`String <String>`[] formats = ``[]``\)
-------------------------------------------------------------------------------------------------------------------------------------

The :ref:`get_file_names <get_file_names>` method scans the files of a directory in a given ``path`` and returns their names in a :ref:`PackedStringArray <PackedStringArray>`. 
The ``formats`` parameter is used to filter what file formats should be included in the final result (without the "."). 
If this parameter is left as default, that means all file formats are included. 
If the ``path`` doesn't point to an existing directory, an error is pushed and the method returns an empty :ref:`PackedStringArray <PackedStringArray>`.


.. _LokFileSystemUtil_get_subdirectory_names:

:ref:`PackedStringArray <PackedStringArray>` get_subdirectory_names\(:ref:`String <String>` path\)
--------------------------------------------------------------------------------------------------

The :ref:`get_subdirectory_names <get_subdirectory_names>` method returns the names of the subdirectories of a directory in a given ``path`` in a :ref:`PackedStringArray <PackedStringArray>`. 
If the ``path`` doesn't point to an existing directory, an error is pushed and the method returns an empty :ref:`PackedStringArray <PackedStringArray>`.


.. _LokFileSystemUtil_directory_is_empty:

:ref:`bool <bool>` directory_is_empty\(:ref:`String <String>` path\)
--------------------------------------------------------------------

The :ref:`directory_is_empty <directory_is_empty>` method looks for the files and subdirectories in the directory in the ``path`` and tells whether that directory is empty or not. 
If the ``path`` doesn't point to an existing directory, an error is pushed and the method returns ``true``, indicating that the directory is empty because it doesn't exist.


.. _LokFileSystemUtil_remove_directory_or_file:

:ref:`int <int>` remove_directory_or_file\(:ref:`String <String>` path\)
------------------------------------------------------------------------

The :ref:`remove_directory_or_file <remove_directory_or_file>` method removes a directory or file from the path specified by the ``path`` parameter. 
If ``path`` points to a directory that isn't empty this method won't succed, so make sure to empty it first. 
If an error occurs, this method pushes it, either way, this method returns an :ref:`@GlobalScope.Error <@GlobalScope_Error>` code specifying the success of the operation.


.. _LokFileSystemUtil_remove_directory_recursive:

:ref:`int <int>` remove_directory_recursive\(:ref:`String <String>` path\)
--------------------------------------------------------------------------

The :ref:`remove_directory_recursive <remove_directory_recursive>` method removes a directory from the path specified by the ``path`` parameter, making sure to remove all the subdirectories or files within it. 
If an error occurs during the operation, this method pushes it and cancels, either way, this method returns an :ref:`@GlobalScope.Error <@GlobalScope_Error>` code specifying the success of the operation.


.. _LokFileSystemUtil_remove_directory_if_exists:

:ref:`int <int>` remove_directory_if_exists\(:ref:`String <String>` path\)
--------------------------------------------------------------------------

The :ref:`remove_directory_if_exists <remove_directory_if_exists>` method uses the :ref:`directory_exists <directory_exists>` and :ref:`remove_directory_or_file <remove_directory_or_file>` methods to remove a directory only if exists. 
If it doesn't exist, this method returns the ``ERR_DOES_NOT_EXIST`` error.


.. _LokFileSystemUtil_remove_directory_recursive_if_exists:

:ref:`int <int>` remove_directory_recursive_if_exists\(:ref:`String <String>` path\)
------------------------------------------------------------------------------------

The :ref:`remove_directory_recursive_if_exists <remove_directory_recursive_if_exists>` method uses the :ref:`directory_exists <directory_exists>` and :ref:`remove_directory_or_file <remove_directory_or_file>` methods to remove a directory only if exists. 
If it doesn't exist, this method returns the ``ERR_DOES_NOT_EXIST`` error.


.. _LokFileSystemUtil_get_directory_name:

:ref:`String <String>` get_directory_name\(:ref:`String <String>` directory_path\)
----------------------------------------------------------------------------------

The :ref:`get_directory_name <get_directory_name>` method is a utility method that grabs the name of a directory from a ``directory_path``.


.. _LokFileSystemUtil_write_or_create_file:

:ref:`int <int>` write_or_create_file\(:ref:`String <String>` path, :ref:`String <String>` content = ``""``\)
-------------------------------------------------------------------------------------------------------------

The :ref:`write_or_create_file <write_or_create_file>` method creates a new file in the path specified by the ``path`` parameter, if it doesn't already exists, else, it simply writes in that file. 
Optionally, this method can receive a ``content`` parameter that defines what should be written in the file. 
If an error occurs during the operation, this method pushes it and cancels, either way, this method returns an :ref:`@GlobalScope.Error <@GlobalScope_Error>` code specifying the success of the operation.


.. _LokFileSystemUtil_write_or_create_encrypted_file:

:ref:`int <int>` write_or_create_encrypted_file\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`String <String>` content = ``""``\)
---------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`write_or_create_encrypted_file <write_or_create_encrypted_file>` method creates a new file in the path specified by the ``path`` parameter, if it doesn't already exist, else, it simply writes in that file using encryption. 
The ``encryption_pass`` parameter is used as the password to encrypt the contents of the file. 
Optionally, this method can receive a ``content`` parameter that defines what should be written in the file. 
If an error occurs during the operation, this method pushes it and cancels, either way, this method returns an :ref:`@GlobalScope.Error <@GlobalScope_Error>` code specifying the success of the operation.


.. _LokFileSystemUtil_create_file_if_not_exists:

:ref:`int <int>` create_file_if_not_exists\(:ref:`String <String>` path\)
-------------------------------------------------------------------------

The :ref:`create_file_if_not_exists <create_file_if_not_exists>` method uses the :ref:`file_exists <file_exists>` and :ref:`write_or_create_file <write_or_create_file>` methods to create a file only if it doesn't already exist. 
If it already exists, this method returns the ``ERR_ALREADY_EXISTS`` error.


.. _LokFileSystemUtil_create_encrypted_file_if_not_exists:

:ref:`int <int>` create_encrypted_file_if_not_exists\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`String <String>` content = ``""``\)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`create_encrypted_file_if_not_exists <create_encrypted_file_if_not_exists>` method uses the :ref:`file_exists <file_exists>` and :ref:`write_or_create_encrypted_file <write_or_create_encrypted_file>` methods to create an encrypted file only if it doesn't already exist. 
If it already exists, this method returns the ``ERR_ALREADY_EXISTS`` error.


.. _LokFileSystemUtil_file_exists:

:ref:`bool <bool>` file_exists\(:ref:`String <String>` path\)
-------------------------------------------------------------

The :ref:`file_exists <file_exists>` method checks if a file exists in the path specified by the ``path`` parameter and returns a ``bool`` indicating the result.


.. _LokFileSystemUtil_read_file:

:ref:`String <String>` read_file\(:ref:`String <String>` path\)
---------------------------------------------------------------

The :ref:`read_file <read_file>` method reads from a file in the path specified by the ``path`` parameter. 
If an error occurs, this method pushes it and returns ``""``, otherwise, it returns the :ref:`String <String>` read from the file.


.. _LokFileSystemUtil_read_encrypted_file:

:ref:`String <String>` read_encrypted_file\(:ref:`String <String>` path, :ref:`String <String>` encryption_pass, :ref:`bool <bool>` suppress_errors = ``false``\)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------

The :ref:`read_encrypted_file <read_encrypted_file>` method reads from a encrypted file in the path specified by the ``path`` parameter. 
The ``encryption_pass`` parameter is used as the password to decrypt the contents of the file. 
If an error occurs, this method pushes it and returns ``""``, otherwise, it returns the :ref:`String <String>` read from the file. 
If the ``suppress_errors`` is ``true``, though, no errors are pushed, except for errors that come from the :ref:`FileAccess.open_encrypted_with_pass <FileAccess_open_encrypted_with_pass>` method.


.. _LokFileSystemUtil_parse_json_from_string:

:ref:`Variant <Variant>` parse_json_from_string\(:ref:`String <String>` string, :ref:`bool <bool>` suppress_errors\)
--------------------------------------------------------------------------------------------------------------------

The :ref:`parse_json_from_string <parse_json_from_string>` method can be used to parse a :ref:`String <String>` into a :ref:`Dictionary <Dictionary>` using a :ref:`JSON <JSON>` instance. 
If the parsing fails, an error is pushed and an empty :ref:`Dictionary <Dictionary>` is returned. 
If the ``suppress_errors`` is ``true``, though, no errors are pushed.


.. _LokFileSystemUtil_load_resources:

:ref:`Resource <Resource>`[] load_resources\(:ref:`String <String>` directory_path, :ref:`String <String>` resource_type = ``""``\)
-----------------------------------------------------------------------------------------------------------------------------------

The :ref:`load_resources <load_resources>` method is a quick way to load all :ref:`Resource <Resource>`s located in a specific ``directory_path``. 
Optionally, a ``resource_type`` :ref:`String <String>` can be passed to filter what types of :ref:`Resource <Resource>`s should be loaded or to prevent unknown file types from being loaded. 
As an example, if a ``"Script"`` :ref:`String <String>` is passed in the ``resource_type`` parameter, only files with formats that can represent :ref:`Script <Script>`s are loaded. 
What formats can represent what :ref:`Resource <Resource>` types are dictated by the :ref:`ResourceLoader.get_recognized_extensions_for_type <ResourceLoader_get_recognized_extensions_for_type>` method.


.. _LokFileSystemUtil_remove_file_if_exists:

:ref:`int <int>` remove_file_if_exists\(:ref:`String <String>` path\)
---------------------------------------------------------------------

The :ref:`remove_file_if_exists <remove_file_if_exists>` method uses the :ref:`file_exists <file_exists>` and :ref:`remove_directory_or_file <remove_directory_or_file>` methods to remove a file only if exists. 
If it doesn't exist, this method returns the ``ERR_DOES_NOT_EXIST`` error.


.. _LokFileSystemUtil_join_file_name:

:ref:`String <String>` join_file_name\(:ref:`String <String>` file_prefix, :ref:`String <String>` file_format\)
---------------------------------------------------------------------------------------------------------------

The :ref:`join_file_name <join_file_name>` method takes a ``file_prefix`` :ref:`String <String>` and a ``file_format`` :ref:`String <String>` and joins them together with a ``"."`` in the middle, so that they form a complete file_name.


.. _LokFileSystemUtil_get_file_name:

:ref:`String <String>` get_file_name\(:ref:`String <String>` file_path\)
------------------------------------------------------------------------

The :ref:`get_file_name <get_file_name>` method is a utility method that grabs the name of a file from a ``file_path``, including its format.


.. _LokFileSystemUtil_get_file_format:

:ref:`String <String>` get_file_format\(:ref:`String <String>` file_name\)
--------------------------------------------------------------------------

The :ref:`get_file_format <get_file_format>` method is a utility method that grabs the format of a file from a ``file_name``. 
The return of this method doesn't include the ``"."`` of the format.


.. _LokFileSystemUtil_get_file_prefix:

:ref:`String <String>` get_file_prefix\(:ref:`String <String>` file_name\)
--------------------------------------------------------------------------

The :ref:`get_file_prefix <get_file_prefix>` method is a utility method that grabs the name of a file without its format. 
The return of this method doesn't include the ``"."`` of the format.

