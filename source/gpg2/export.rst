.. _gpg2-export:

Export
======

How to backup your keys.

Public Key
----------

.. code:: bash

   gpg2 --export --armor CCCCCCCCCCCCCCCC > pubkey.ascii

Full Key
--------

(including private part, probably what you are looking for)

.. code:: bash

   gpg2 --export-secret-key --armor CCCCCCCCCCCCCCCC > fullkey.ascii

.. note::

   An exported private key, e.g. stored on a USB stick is unprotected if you loose they storage media.
   You can encrypt and decrypt the backup file with a simple password via:
   
   .. code:: bash
   
      # encrypt with password
      gpg -c fullkey.ascii
      # generates an encrypted fullkey.ascii.gpg file
      rm fullkey.ascii

      # descrypt with password
      gpg -d fullkey.ascii.gpg > fullkey.ascii
      # generates a decrypted fullkey.ascii file

Stubs
-----

(for keys moved to smartcards)
