.. _background-renew:

Renewal
=======

There are several ways to "renew" the lifetime of existing keys.
This chapter informs about several common ones and their pros/cons (to do).

Keep Key, Extend Deadline
-------------------------

* pro: easy update & publication
* pro: no new signatures needed
* con: adds no forward secrecy

Keep Primary Key, Update Subkeys
--------------------------------

* pro: no new signatures needed
* neutral: update process a bit more complex
* unclear: adds (no) forward secrecy?

Generate New Primary Key, Sign with old Primary
-----------------------------------------------

* pro: forward secrecy from this point onward
* neutral: update process a bit more complex
* con: only transitive trust from old key
