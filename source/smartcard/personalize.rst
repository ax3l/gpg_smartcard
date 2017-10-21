.. _smartcard-personalize:

Personalize
===========

Is this even useful?

.. code:: bash

   gpg2 --card-edit
   # ...

   gpg/card> admin
   Admin commands are allowed

   gpg/card> passwd
   # ...

   gpg/card> name
   Cardholder's surname: Doe
   Cardholder's given name: Jane

   gpg/card> lang
   Language preferences: en

   gpg/card> url
   URL to retrieve public key: https://.../CCC.txt

   gpg/card> sex
   Sex ((M)ale, (F)emale or space): f

   gpg/card> login
   Login data (account name): jane

   gpg/card> quit

See [YubiEdit]_
