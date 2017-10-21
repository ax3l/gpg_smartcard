.. _background-devicegen:

Key Generation on Device
========================

Pros
----

* key never leaves the device
* very easy setup, e.g. integrated in Enigmail

Cons
----

* backup possible on generation if at all?
* entropy and RNG on device need to be trustworthy (often issues)
* recent Infineon RSA key issues can also weaken such generated keys
  `[1] <https://www.yubico.com/2017/10/infineon-rsa-key-generation-issue/>`_,
  `[2] <https://www.yubico.com/support/security-advisories/ysa-2017-01/>`_

How
---

.. code:: bash

   # start the edit of the smartcard
   gpg2 --card-edit

   generate

Notes
-----

The `GPG manual <https://www.gnupg.org/howtos/card-howto/en/ch03s03.html>`_ on ``--card-edit`` lists the possibility to store a off-device backup on ``generate``.
Unclear: Is this possible with all devices?
