.. _keygen-subkeys:

Create Subkeys
==============

... on your local laptop.

.. note::

   Reminder from ``gpg2 --list-secet-keys``:

   .. code::

      sec   rsa4096/0xCCCCCCCCCCCCCCCC 2015-02-01 [SCA] [expires: 2020-01-31]
      # ...

.. code:: bash

   gpg2 --expert --edit-key CCCCCCCCCCCCCCCC

   gpgp> addkey
   # select 8 add a new RSA sub-key to your key
   # select A, then S, then E to get a pure authentication key. Then Q to continue.
   # select same expiry as for the rest of the key and then answer y to save changes.

   gpg> quit
