.. _smartcard-import:

Import
======

Full key to stub key...

.. warning::

   Importing a GPG key to a smart-card is a *one-way operation* for your private key!
   Backup your *full key* via an :ref:`export first <gpg2-export>`!

.. note::

   Reminder from ``gpg2 --list-secret-keys`` after we created a :ref:`sub-keys <keygen-subkeys>`.

   .. code::

      sec   rsa4096/0xCCCCCCCCCCCCCCCC 2015-02-01 [SC] [expires: 2020-01-31]
      uid                   [...]
      ssb   rsa4096/0xEEEEEEEEEEEEEEEE 2015-02-01 [E] [expires: 2020-01-31]
      ssb   rsa4096/0xAAAAAAAAAAAAAAAA 2015-02-01 [A] [expires: 2020-01-31]

.. code:: bash

   gpg2 --edit-key CCCCCCCCCCCCCCCC

   # move primary key to signature key slot on card
   gpg> toggle
   gpg> keytocard
   # select: (1) Signature key

   # repeat for encryption key
   gpg> key 1
   gpg> keytocard
   # select: (2) Encryption sub-key

   # repeat for authentication sub-key
   gpg> key 2
   gpg> keytocard
   # select: (3) Authentication key

   gpg> quit
   # Save changes? (y/N) y

   gpg2 --list-secret-keys
   # [...]
   # ssb* [...]


See [YubiImport]_ and [YubiEdit]_

.. [YubiImport]
   https://developers.yubico.com/PGP/Importing_keys.html

.. [YubiEdit]
   https://developers.yubico.com/PGP/Card_edit.html
