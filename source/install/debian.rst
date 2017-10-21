.. _install-debian:

Debian 9 "stretch"
==================

General
-------

.. code:: bash

   apt-get install gnupg2 libu2f-host0

Yubikey
-------

.. code:: bash

   apt-get install yubikey-personalization-gui

Test [YubiEdit]_:

.. code:: bash

   lsusb -v
   # Yubikey listed?

   # ykpersonalize -m6
   # ...

   # gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
   # ...

Nitrokey
--------

...
