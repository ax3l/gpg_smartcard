.. _gpg2-list:

List
====

Owned Keys
----------

Keys that you own (aka: you have access to the private keys)

.. code:: bash

   gpg2 --list-secret-keys

Interpret Output
----------------

.. code::

   sec   rsa4096/0xCCCCCCCCCCCCCCCC 2015-02-01 [SCA] [expires: 2020-01-31]
         FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
   uid                   [ultimate] Jane Roe <jane@roe.de>
   uid                   [ultimate] Dr. Jane Roe <j.roe@esa.int>
   ssb   rsa4096/0xEEEEEEEEEEEEEEEE 2015-02-01 [E] [expires: 2020-01-31]

.. note::

   to do: what means what
