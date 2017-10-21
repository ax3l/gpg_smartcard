.. _install-debian:

Debian 9 "stretch"
==================

General
-------

.. code:: bash

   apt-get install gnupg2 gnupg-agent pcscd pcsc-tools scdaemon libusb-1.0-0

Yubikey
-------

.. code:: bash

   apt-get install libu2f-host0 yubikey-personalization-gui

Test [YubiEdit]_:

.. code:: bash

   lsusb -v
   # Yubikey listed?

   # ykpersonalize -m6
   # ...

   # gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
   # ...

Further references
""""""""""""""""""

* https://github.com/drduh/YubiKey-Guide/find/master#install---linux
* https://developers.yubico.com/libu2f-host/

Nitrokey
--------

...
