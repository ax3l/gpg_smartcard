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

Further initial setup needs explained in [YubiEdit]_:

.. code:: bash

   # check USB devices
   lsusb
   # Yubikey listed?

   # make sure CCID mode is enabled
   ykpersonalize -m6

   # check smart card readers
   # pcsc_scan
   # Yubikey listed?

   # connect to key's GPG app and output version
   gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
   # D[0000]  04 03 04 90 00
   # OK
   # -> means: v4.3.4

Further references
""""""""""""""""""

* https://github.com/drduh/YubiKey-Guide/find/master#install---linux
* https://developers.yubico.com/libu2f-host/

Nitrokey
--------

...
