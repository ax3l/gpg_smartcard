.. _gpg2-list:

List
====

Owned Keys
----------

Keys that you own (aka: you have access to the private keys)

.. code:: bash

   gpg2 --list-secret-keys

Interpret Output
----------------

.. code-block:: none
   :linenos:

   sec   rsa4096/0xCCCCCCCCCCCCCCCC 2015-02-01 [SCA] [expires: 2020-01-31]
         FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
   uid                   [ultimate] Jane Roe <jane@roe.de>
   uid                   [ultimate] Dr. Jane Roe <j.roe@esa.int>
   ssb   rsa4096/0xEEEEEEEEEEEEEEEE 2015-02-01 [E] [expires: 2020-01-31]

Line-By-Line
""""""""""""

* line 1: the *primary key*
* line 2: fingerprint
* line 3-4: user IDs of the key (optional, used in Web-of-Trust and for Certification)
* line 5: the first *subkey*

Column-By-Column
""""""""""""""""

**1st column:**

* ``sec``: ... (secret key available?)
* ``ssb``: ... (secret key of a subkey available?)

* ``ssb*``: currently selected subkey during edits
  (next section: selected via ``gpg2 --edit-key CCCCCC`` - ``key N``)
* ``ssb>``: only stub of a subkey is available
  (next section: after secret part has been moved to a smartcard)
* ``sec#``: the secret part is not available
  (removed from local key store)

* ``uid``: this line is a user ID

**2nd column:**

* ``algorithm/0xKeyID``

**3rd column:**

* date of generation

**4th column:**

* ``[...]```: capabilities (see below)

**5th column:**

* date of expiration

Capabilities
""""""""""""

Noted in each key with ``[...]``.
Can be delegated from the primary key to subkeys.

**S**: Sign.
Signs data, such as e-mails.

**C**: Certification.
Certifies (also: "signs") keys, e.g. keys of other people at a crypto party or during subkey generation.
All primary keys *must* have this capability.

**A**: Authenticate.
Can be used for logins such as SSH.

**E**: Encrypt.
Encrypts (and decrypts?) data.

.. note::

   to do: document each entry/line
