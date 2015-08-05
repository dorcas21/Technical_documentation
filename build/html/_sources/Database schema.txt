Database Schema
=========================

This describes the characteristics of the tables and the columns in the Supply Chain Tool; including datatypes and sizes, nullability, index, sequence, key and constraint information.

Here is a screenshot of how the database schema looks like.

.. figure:: images/schema.png


Database Tables
---------------

#. Central sites

#. Counties

#. Datasets

#. Deletion_logs

#. Dhis_datasets

#. Facilities

#. Facility_program_mapping

#. Login

#. Programs

#. Satellite_site

#. Standalone_site

#. Sub_counties

#. Sub_county_stores

#. Top_level

#. Users




Tables' Attributes and Design
------------------------------

central_sites
~~~~~~~~~~~~~~

This table consists of a list of central sites.

The only attribute present in the table is the central id. The other details concerning central sites are captured from DHIS2 through the web API.

This is how the table looks;

+------------+--------------+------+-----+---------+-------+
| Field      | Type         | Null | Key | Default | Extra |
+============+==============+======+=====+=========+=======+
| central_id | varchar(255) | NO   | PRI | NULL    |       |
+------------+--------------+------+-----+---------+-------+


Counties
~~~~~~~~

This table consists the following attributes:

 * County_id

 * County_name

 * Parent_id

This is how it looks like

+-------------+--------------+------+-----+---------+-------+
| Field       | Type         | Null | Key | Default | Extra |
+=============+==============+======+=====+=========+=======+
| county_id   | varchar(50)  | NO   | PRI | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| county_name | varchar(200) | NO   |     | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| parent_id   | varchar(50)  | NO   | MUL | NULL    |       |
+-------------+--------------+------+-----+---------+-------+


Datasets
~~~~~~~~~

This table stores the datasets used in the application. It contains the following attributes:

  * Dataset_id

  * Program_id

  * Created_on

  * Created_by

  * Comment


+------------+--------------+------+-----+---------+----------------+
| Field      | Type         | Null | Key | Default | Extra          |
+============+==============+======+=====+=========+================+
| id         | int(11)      | NO   | PRI | NULL    | auto_increment |
+------------+--------------+------+-----+---------+----------------+
| dataset_id | varchar(255) | NO   | MUL | NULL    |                |
+------------+--------------+------+-----+---------+----------------+
| program_id | int(11)      | NO   | MUL | NULL    |                |
+------------+--------------+------+-----+---------+----------------+
| created_on | varchar(255) | NO   |     | NULL    |                |
+------------+--------------+------+-----+---------+----------------+
| created_by | varchar(255) | NO   | MUL | NULL    |                |
+------------+--------------+------+-----+---------+----------------+
| comment    | varchar(255) | NO   |     | NULL    |                |
+------------+--------------+------+-----+---------+----------------+




Deletion_logs
~~~~~~~~~~~~~~

This table consists of the following attributes:

  * Id

  * Number_deleted

  * Deleted_item_id

  * Deleted_item_name

  * Deleted_item_description

  * Date_deleted

  * Deleted_by 




+--------------------------+---------------+------+-----+---------+----------------+
| Field                    | Type          | Null | Key | Default | Extra          |
+==========================+===============+======+=====+=========+================+
| id                       | int(11)       | NO   | PRI | NULL    | auto_increment |
+--------------------------+---------------+------+-----+---------+----------------+
| number_deleted           | varchar(255)  | NO   |     | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+
| deleted_item_id          | varchar(255)  | NO   |     | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+
| deleted_item_name        | varchar(255)  | NO   |     | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+
| deleted_item_description | varchar(5000) | NO   |     | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+
| date_deleted             | varchar(255)  | NO   |     | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+
| deleted_by               | varchar(50)   | NO   | MUL | NULL    |                |
+--------------------------+---------------+------+-----+---------+----------------+




Dhis_datasets
~~~~~~~~~~~~~~

The attributes in the table are:

  * Dataset_id

  * Dataset_name

  * Dataset_href

  * Dataset_code



+--------------+--------------+------+-----+---------+-------+
| Field        | Type         | Null | Key | Default | Extra |
+==============+==============+======+=====+=========+=======+
| dataset_id   | varchar(255) | NO   | PRI | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
| dataset_name | varchar(255) | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
| dataset_href | varchar(255) | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
| dataset_code | varchar(255) | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+


Facilities
~~~~~~~~~~

The table consists of the following attributes:

  * Facility_id

  * Facility_name

  * Parent_id

  * Mfl_code


+---------------+--------------+------+-----+---------+-------+
| Field         | Type         | Null | Key | Default | Extra |
+===============+==============+======+=====+=========+=======+
| facility_id   | varchar(50)  | NO   | PRI | NULL    |       |
+---------------+--------------+------+-----+---------+-------+
| facility_name | varchar(200) | NO   |     | NULL    |       |
+---------------+--------------+------+-----+---------+-------+
| parent_id     | varchar(50)  | NO   | MUL | NULL    |       |
+---------------+--------------+------+-----+---------+-------+
| mfl_code      | varchar(50)  | NO   | MUL | NULL    |       |
+---------------+--------------+------+-----+---------+-------+




Facility_program_mapping
~~~~~~~~~~~~~~~~~~~~~~~~~

The table contains the following attributes:

  * Mapping_id

  * Facility_id

  * Program_id

  * Classification

  * Created_on

  * Created_by

  * Comment





+----------------+--------------+------+-----+---------+----------------+
| Field          | Type         | Null | Key | Default | Extra          |
+================+==============+======+=====+=========+================+
| mapping_id     | int(11)      | NO   | PRI | NULL    | auto_increment |
+----------------+--------------+------+-----+---------+----------------+
| facility_id    | varchar(255) | NO   | MUL | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+
| program_id     | int(11)      | NO   | MUL | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+
| classification | varchar(255) | NO   |     | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+
| created_on     | varchar(255) | NO   |     | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+
| created_by     | varchar(255) | NO   | MUL | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+
| comment        | varchar(255) | NO   |     | NULL    |                |
+----------------+--------------+------+-----+---------+----------------+




Login
~~~~~~

The attributes of the table include:

  * Login_id

  * Username

  * Password

  * Role

  * User_id

  * Account_created

  * Account_created_by

  * Details_last_updated

  * Details_last_updated_by

  * Password_expiry

  * Password_status

  * Password_last_updated

  * Password_last_updated_by

  * Account_status

  * Account_status_last_updated

  * Account_status_updated_by

  * Last_login




+-----------------------------+--------------+------+-----+---------+----------------+
| Field                       | Type         | Null | Key | Default | Extra          |
+-----------------------------+--------------+------+-----+---------+----------------+
| login_id                    | int(11)      | NO   | PRI | NULL    | auto_increment |
+-----------------------------+--------------+------+-----+---------+----------------+
| username                    | varchar(50)  | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| password                    | varchar(50)  | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| role                        | varchar(50)  | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| user_id                     | varchar(50)  | YES  | MUL | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| account_created             | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| account_created_by          | varchar(50)  | NO   | MUL | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| details_last_updated        | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| details_last_updated_by     | varchar(50)  | NO   | MUL | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| password_expiry             | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| password_status             | varchar(50)  | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| password_last_updated       | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| password_last_updated_by    | varchar(50)  | NO   | MUL | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| account_status              | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| account_status_last_updated | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| account_status_updated_by   | varchar(50)  | NO   | MUL | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+
| last_login                  | varchar(255) | NO   |     | NULL    |                |
+-----------------------------+--------------+------+-----+---------+----------------+



Programs
~~~~~~~~~


The table contains programs with the following attributes:

  * Program_id

  * Program_name

  * Date_created

  * Created_by

  * Date_updated

  * Updated_by

  * Comment



+--------------+--------------+------+-----+---------+----------------+
| Field        | Type         | Null | Key | Default | Extra          |
+==============+==============+======+=====+=========+================+
| program_id   | int(255)     | NO   | PRI | NULL    | auto_increment |
+--------------+--------------+------+-----+---------+----------------+
| program_name | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| date_created | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| created_by   | varchar(255) | NO   | MUL | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| date_updated | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| updated_by   | varchar(255) | NO   | MUL | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| comment      | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+





Satellite_site
~~~~~~~~~~~~~~~
This table stores the satellite sites with the following attributes.

  * Satellite_id

  * Central_id

The data is obtained from the web API and stored in this table.


+-------------+--------------+------+-----+---------+-------+
| Field       | Type         | Null | Key | Default | Extra |
+=============+==============+======+=====+=========+=======+
| satelite_id | varchar(255) | NO   | PRI | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| central_id  | varchar(255) | NO   | MUL | NULL    |       |
+-------------+--------------+------+-----+---------+-------+



Standalone_site
~~~~~~~~~~~~~~~~

This is how the table looks like:

+---------------+--------------+------+-----+---------+-------+
| Field         | Type         | Null | Key | Default | Extra |
+---------------+--------------+------+-----+---------+-------+
| standalone_id | varchar(255) | NO   | PRI | NULL    |       |
+---------------+--------------+------+-----+---------+-------+


Sub_counties
~~~~~~~~~~~~

This table contains the sub-counties with the following attributes:

* Sub_county_id

* Sub_county_name

* Parent_id




+-----------------+--------------+------+-----+---------+-------+
| Field           | Type         | Null | Key | Default | Extra |
+=================+==============+======+=====+=========+=======+
| sub_county_id   | varchar(50)  | NO   | PRI | NULL    |       |
+-----------------+--------------+------+-----+---------+-------+
| sub_county_name | varchar(200) | NO   |     | NULL    |       |
+-----------------+--------------+------+-----+---------+-------+
| parent_id       | varchar(50)  | NO   | MUL | NULL    |       |
+-----------------+--------------+------+-----+---------+-------+


Sub_county_stores
~~~~~~~~~~~~~~~~~~

The sub-county stores table looks like this:


+---------------------+--------------+------+-----+---------+-------+
| Field               | Type         | Null | Key | Default | Extra |
+=====================+==============+======+=====+=========+=======+
| sub_county_store_id | varchar(255) | NO   | PRI | NULL    |       |
+---------------------+--------------+------+-----+---------+-------+



Top_level
~~~~~~~~~~


The table has **id** and **name** as its attributes:


+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+=======+==============+======+=====+=========+=======+
| id    | varchar(50)  | NO   | PRI | NULL    |       |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(200) | NO   |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+



Users
~~~~~~

The users table contains:

  * User_identifier

  * Name

  * Gender

  * Email

  * Mobile_no

  * Date_created

  * Created_by

  * Details_last_updated

  * Details_updated_by


+----------------------+--------------+------+-----+---------+-------+
| Field                | Type         | Null | Key | Default | Extra |
+======================+==============+======+=====+=========+=======+
| user_identifier      | varchar(50)  | NO   | PRI | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| name                 | varchar(50)  | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| gender               | varchar(50)  | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| email                | varchar(50)  | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| mobile_no            | varchar(50)  | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| date_created         | varchar(255) | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| created_by           | varchar(50)  | NO   | MUL | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| details_last_updated | varchar(255) | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+
| details_updated_by   | varchar(50)  | NO   |     | NULL    |       |
+----------------------+--------------+------+-----+---------+-------+




.. The project contains three parts: api, assets, client, db.

.. Each part forms an important part of this project.

.. api
.. ----

.. These are PHP5_CURL scripts that interact with the DHIS2 API.
.. Data querying from DHIS2 API and some level of processing is done here.


.. Assets
.. ------
.. These are the resources needed in this project. 

.. It contains the JavaScript, CSS, Bootstrap, Font-Awesome scripts.

.. Client
.. ------
.. This is the presentation and user interface logic. 

.. It contains scripts that will display on the browser.

.. db
.. --
.. This is the database logic. It contains scripts for database authentication and connection creation as well as those for inserting, fetching and updating items on the database.

.. System
.. -------

.. This is the system environment variables. It contains parameters that need to be set for the system to run once deployed.

.. They include the database authentication and connection creation.

.. Edit the config (config.php) file to reflect your local environment.

.. The projects landing page is index.php which is located at its root. It is the login page.




.. .. Interoperability
.. .. ------------------
.. .. This system adopts an **API First** approach, as explained in the :doc:`06_api`
.. .. chapter.

.. .. The authors have gone to great lengths to make it easy for other systems
.. .. - with the correct authorization - to read and write MFL data.

.. .. Standardization
.. .. -----------------
.. .. The MFL's core mission includes the standardization of facility codes. In this
.. .. edition, the core mission has been expanded to include the standardization of
.. .. service codes. You can read more about that in the :doc:`09_services` chapter.

.. .. Unification
.. .. --------------
.. .. The first generation of the Master Facilities List ( and its "satellites" )
.. .. had five semi-independent systems: public and administration systems for the
.. .. "core" MFL, a mirror of those two for the Master Community Units List and
.. .. a regulators interface.

.. .. This release unifies them all under a single API. That API is client agnostic
.. .. - the client could be a web or mobile application, another system or even a
.. .. reporting tool.

.. .. .. note::

.. ..     A future release of this system could standardize more things e.g
.. ..     practitioner codes.

.. toctree::
    :maxdepth: 2
