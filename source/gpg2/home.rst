.. _gpg2-home:

Change Home Directory
=====================

By default, all ``gpg2`` configuration data resides in ``$HOME/.gnupg/``.

If you want to experiment with GPG, test a new smartcard or follow this document, you can also create a temporary new location to experiment with.
This prevents accidentially editing/deleting/modifying your already existing keys and to work from a live system or on an "offline" USB stick.

.. code:: bash

   # assuming the directory exists,
   # otherwise create it with
   #   mkdir /media/my-usb-stick/my-gpg-home/
   #   chmod -R og-rwx /media/my-usb-stick/my-gpg-home/
   export GNUPGHOME=/media/my-usb-stick/my-gpg-home/

This setting is valid until you close your terminal.

The directory should only be accessible by the current user (see ``chmod`` comment above), otherwise you will see warnings of the form ``# gpg: WARNING: unsafe permissions on homedir '/media/my-usb-stick/my-gpg-home/'``.

.. note::

   On the first call to ``gpgp2`` with a changed (fresh) home it will create a "keybox" (``pubring.kbx``) and a "trustdb" (``trustdb.gpg``).
   
   .. code:: bash

      gpg2 --list-secret-keys
      
      # gpg: keybox '/media/my-usb-stick/my-gpg-home/pubring.kbx' created
      # gpg: /media/my-usb-stick/my-gpg-home/trustdb.gpg: trustdb created
