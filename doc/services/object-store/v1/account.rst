Account
=======

Show account details
--------------------

To work with an Object Store account, you must first retrieve an account object like so:

.. sample:: object_store/v1/account/get.php

Get account metadata
--------------------

.. sample:: object_store/v1/account/get_metadata.php

Replace all metadata with new values
------------------------------------

In order to replace all existing metadata with a set of new values, you can use this operation. Any existing metadata
items which not specified in the new set will be removed. For example, say an account has the following metadata
already set:

::

    Foo: value1
    Bar: value2

and you *reset* the metadata with these values:

::

    Foo: value4
    Baz: value3

the metadata of the account will now be:

::

    Foo: value4
    Baz: value3

To merge metadata, you must run:

.. sample:: object_store/v1/account/reset_metadata.php

Merge new metadata values with existing
---------------------------------------

In order to merge a set of new metadata values with the existing metadata set, you can use this operation. Any existing
metadata items which are not specified in the new set will be preserved. For example, say an account has the following
metadata already set:

::

    Foo: value1
    Bar: value2

and you merge them with these values:

::

    Foo: value4
    Baz: value3

the metadata of the account will now be:

::

    Foo: value4
    Bar: value2
    Baz: value3

To reset metadata, you must run:

.. sample:: object_store/v1/account/merge_metadata.php