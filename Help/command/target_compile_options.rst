target_compile_options
----------------------

Add compile options to a target.

.. code-block:: cmake

  target_compile_options(<target> [BEFORE]
    <INTERFACE|PUBLIC|PRIVATE> [items1...]
    [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])

Adds options to the :prop_tgt:`COMPILE_OPTIONS` or
:prop_tgt:`INTERFACE_COMPILE_OPTIONS` target properties. These options
are used when compiling the given ``<target>``, which must have been
created by a command such as :command:`add_executable` or
:command:`add_library` and must not be an :ref:`ALIAS target <Alias Targets>`.

Arguments
^^^^^^^^^

If ``BEFORE`` is specified, the content will be prepended to the property
instead of being appended.

The ``INTERFACE``, ``PUBLIC`` and ``PRIVATE`` keywords are required to
specify the :ref:`scope <Target Usage Requirements>` of the following arguments.
``PRIVATE`` and ``PUBLIC`` items will populate the :prop_tgt:`COMPILE_OPTIONS`
property of ``<target>``.  ``PUBLIC`` and ``INTERFACE`` items will populate the
:prop_tgt:`INTERFACE_COMPILE_OPTIONS` property of ``<target>``.
The following arguments specify compile options.  Repeated calls for the same
``<target>`` append items in the order called.

.. versionadded:: 3.11
  Allow setting ``INTERFACE`` items on :ref:`IMPORTED targets <Imported Targets>`.

.. |command_name| replace:: ``target_compile_options``
.. include:: GENEX_NOTE.txt

.. include:: OPTIONS_SHELL.txt

See Also
^^^^^^^^

* This command can be used to add any options. However, for adding
  preprocessor definitions and include directories it is recommended
  to use the more specific commands :command:`target_compile_definitions`
  and :command:`target_include_directories`.

* For directory-wide settings, there is the command :command:`add_compile_options`.

* For file-specific settings, there is the source file property :prop_sf:`COMPILE_OPTIONS`.

* :command:`target_compile_features`
* :command:`target_link_libraries`
* :command:`target_link_directories`
* :command:`target_link_options`
* :command:`target_precompile_headers`
* :command:`target_sources`
