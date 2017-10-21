.. _smartcard-personalize:

Personalize
===========

You can personalize some of the meta information of your smartcard directly via the gpg2 interface.
This allows you to, e.g. set passwords or additional meta information.

.. code:: bash

   # start the edit of the smartcard
   gpg2 --card-edit

   gpg/card> admin
   Admin commands are allowed

   gpg/card> passwd
   # ...

   # setting a URL for a public key dramatically easens the startup
   # needs when connecting the smartcard to an other device
   # (laptop, Android Cell Phone with OpenKeyChain) since the pub
   # key is not installed on the device
   gpg/card> url
   URL to retrieve public key: http://.../CCC.txt
   # note: You can set a normal https:// url to your private website
   #       here but it will not work with older versions of GPG

   # the options below are purely administrational if you have several
   # smartcards or want to use them in specific workflows.
   # the information are not authenticated in any way and optional
   gpg/card> name
   Cardholder's surname: Doe
   Cardholder's given name: Jane

   gpg/card> lang
   Language preferences: en

   gpg/card> sex
   Sex ((M)ale, (F)emale or space): f

   gpg/card> login
   Login data (account name): jane

   gpg/card> quit

References
""""""""""

* [YubiEdit]_
* https://www.gnupg.org/howtos/card-howto/en/ch03s03.html
