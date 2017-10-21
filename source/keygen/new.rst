.. _keygen-new:

Create a Key
============

... on your local laptop.

.. code:: bash

   gpg2 --gen-key ...

Revocation Key
--------------

.. note::

   A revocation key is not sensitive for encrypted data.
   Still, anyone who can access your revocation keys can publicly and provably mark your keys as invalid.
   For most use cases, just keep is as safe as your :ref:`privaye key backups <gpg2-export>`.
