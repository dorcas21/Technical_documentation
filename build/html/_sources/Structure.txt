Project structure
=========================
The project contains three parts: api, assets, client, db.

Each part forms an important part of this project.

api
----

These are PHP5_CURL scripts that interact with the DHIS2 API.
Data querying from DHIS2 API and some level of processing is done here.


Assets
------
These are the resources needed in this project. 

It contains the JavaScript, CSS, Bootstrap, Font-Awesome scripts.

Client
------
This is the presentation and user interface logic. 

It contains scripts that will display on the browser.

db
--
This is the database logic. It contains scripts for database authentication and connection creation as well as those for inserting, fetching and updating items on the database.

System
-------

This is the system environment variables. It contains parameters that need to be set for the system to run once deployed.

They include the database authentication and connection creation.

Edit the config (config.php) file to reflect your local environment.

The projects landing page is index.php which is located at its root. It is the login page.




.. Interoperability
.. ------------------
.. This system adopts an **API First** approach, as explained in the :doc:`06_api`
.. chapter.

.. The authors have gone to great lengths to make it easy for other systems
.. - with the correct authorization - to read and write MFL data.

.. Standardization
.. -----------------
.. The MFL's core mission includes the standardization of facility codes. In this
.. edition, the core mission has been expanded to include the standardization of
.. service codes. You can read more about that in the :doc:`09_services` chapter.

.. Unification
.. --------------
.. The first generation of the Master Facilities List ( and its "satellites" )
.. had five semi-independent systems: public and administration systems for the
.. "core" MFL, a mirror of those two for the Master Community Units List and
.. a regulators interface.

.. This release unifies them all under a single API. That API is client agnostic
.. - the client could be a web or mobile application, another system or even a
.. reporting tool.

.. .. note::

..     A future release of this system could standardize more things e.g
..     practitioner codes.

.. toctree::
    :maxdepth: 2
