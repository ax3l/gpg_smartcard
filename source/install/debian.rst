.. _install-debian:

Debian 9 "stretch"
==================

General
-------

.. code:: bash

   apt-get install gnupg2 gnupg-agent pcscd pcsc-tools scdaemon libusb-1.0-0 libccid
   service udev restart

Yubikey
-------

.. code:: bash

   apt-get install libu2f-host0 yubikey-personalization yubikey-personalization-gui ykneomgr
   service udev restart

Further initial setup needs explained in [YubiEdit]_:

.. code:: bash

   # check USB devices
   lsusb
   # Yubikey listed?

   # make sure CCID mode is enabled
   # note: -m86 is also possible, it enables all modes
   ykpersonalize -m6

   # check basic information of your yubikey
   ykinfo -a

   # check smart card readers
   # pcsc_scan
   # Yubikey listed?

   # connect to key's GPG app and output version
   gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
   # D[0000]  04 03 04 90 00
   # OK
   # -> means: v4.3.4

   # OpenPGP Version 1 or 2 card?
   gpg2 --card-status | grep Version
   # Version ..........: 2.1

Nitrokey
--------

...

Further references
------------------

* https://wiki.fsfe.org/TechDocs/CardHowtos/CardWithSubkeysUsingBackups
* https://github.com/drduh/YubiKey-Guide/find/master#install---linux
* https://developers.yubico.com/libu2f-host/
* http://wiki.yobi.be/wiki/GnuPG (includes trouble shooting)
* https://www.nitrokey.com/documentation/installation
* GUI: `Gnu Privacy Assistant (GPA) <https://www.nitrokey.com/setup-gnu-privacy-assistant-gpa>`_
