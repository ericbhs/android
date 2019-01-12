===================
Multiple activities
===================

.. contents:: :local:

Core elements
=============

* ``Activity`` : a rectangular area that displays something
* ``Intent`` : an action being requested that the device should try to perform
* ``IntentService`` : services that can handle ``Intent`` requests and process the work to be done
* ``BroadcastReceivers`` : receives an ``Intent`` from a ``sendBroadcast`` method, often indicating that some work has been completed.

Functions / Objects
===================

* ``Intent`` : an action being requested that the device should try to perform
* ``getIntent()`` : gets the ``Intent`` that was passed to an activity
* ``putExtra()`` : passes data as a (key - value) pair
* ``getExtras().getString()`` : retrieves the ``String`` that was passed to the ``Intent`` object
* ``startActivity()`` : used to launch another activity