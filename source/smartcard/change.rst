.. _smartcard-change-device:

Change Device
=============

If you are moving with your configured smartcard to another device, its GPG keyring needs to learn the key before the card can be used.
The fastest way to achieve this is to retreive the public key as configured in the smartcard.

.. code:: bash

   gpg2 --edit-card

   # receive key stubs from URL
   gpg> fetch
   gpg> quit

   gpg2 --list-keys
   # now visible
   gpg2 --list-secret-keys
   # [...]
   # ssb* [...]
