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

Capabilities
""""""""""""

Noted in each key with ``[...]``.
Can be delegated from the primary key to subkeys.

**S**: Sign.
Signs data, such as e-mails.

**C**: Certification.
Certifies (also: "signs") keys, e.g. keys of other people at a crypto party or during subkey generation.
All primary keys *must* have this capability.

**A**: Authenticate.
Can be used for logins such as SSH.

**E**: Encrypt.
Encrypts (and decrypts?) data.

.. note::

   to do: document each entry/line
