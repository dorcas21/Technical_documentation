Deployment Process 
============================

Introduction
-------------
Linux-Ubuntu server is the preferred development and deployment environment for this application. 

The Dependencies-Development and Production environment required are:

#. Git- This is a distributed revision control system.

#. MySQL  database(>5.5), apache server and php(>=5.3)-LAMP.

#. php-curl.

#. crontab.


Installation
-------------

#. Install all the depencies i.e the ones listed above in your machine.

How to install Git:
++++++++++++++++++++

If you are using ubuntu, just type the following commands in the ubuntu terminal;

  **sudo apt-get update**

  **sudo apt-get install git**

Now that you have git installed, you need to do a few things so that the commit messages that will be generated for you will contain your correct information.  

The easiest way of doing this is through the git config command. Specifically, we need to provide our name and email address because git embeds this information into each commit we do. We can go ahead and add this information by typing:

  **git config --global user.name "Your Name"**

  **git config --global user.email "youremail@domain.com"**

To learn more about git, you can follow the link `how to use git effectively`_ 

.. _`how to use git effectively`: https://www.digitalocean.com/community/tutorials/how-to-use-git-effectively

If you are using windows, You'll need to download and install `Git for Windows`_. If you're unsure of which one to choose, just go with the full installer. After downloading, run the installer. 

.. _`Git for Windows`: http://msysgit.github.io/


How to install LAMP:
+++++++++++++++++++++

LAMP stack is a group of open source software used to get web servers up and running. The acronym stands for Linux, Apache, MySQL, and PHP.

First, you need to install Apache.

  **sudo apt-get update**

  **sudo apt-get install apache2**

That’s it. To check if Apache is installed, direct your browser to your server’s IP address (eg. http://12.34.56.789). The page should display the words “It works!"   

Secondly, install MYSQL bt typing the following commands,

  **sudo apt-get install mysql-server libapache2-mod-auth-mysql php5-mysql**

Once you have installed MySQL, we should activate it with this command:  

  **sudo mysql_install_db**

Finish up by running the MySQL set up script:

  **sudo /usr/bin/mysql_secure_installation**

The prompt will ask you for your current root password.

  **Enter current password for root (enter for none):**

  **OK, successfully used password, moving on...**


Thirdly, you need to install PHP.

Type this command on the terminal;

  **sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt**


How to install PHP-Curl:
+++++++++++++++++++++++++

Simply type the following command from the terminal

  **sudo apt-get install php5-curl**


How to use crontab:
++++++++++++++++++++

A crontab is a simple text file with a list of commands meant to be run at specified times. It is edited with a command-line utility. These commands (and their run times) are then controlled by the cron daemon, which executes them in the system background.

To access crontab, type in the following command,

  **crontab -e**


If you need to run commands with administrative privileges,

  **sudo crontab -e**

To list crontab content,

  **crontab -l**






2. Clone the application from the github repository to your document root in your machine/Or Copy the application folder into your document root.

.. note::

    Please note that you must have an account on Github in order to do this.


Setup and Configuration
------------------------

#. Create a mysql database from your localhost and dump the database schema  into it.( Database Schema is in  the application’s root folder).

#. In the *config.php* file (application_name/system) change the configurations for:

  * MySQL Database name.

  * MySQL user and the MySQL password.

  * Base path for your application.

  * DHIS2 url

  * DHIS2 access username and password for api interaction. 


.. figure:: images/config.png  


3. Setup a cronjob to download data elements from DHIS2.(Executes hourly).

  * api/download_dataElements.php

.. figure:: images/cron.png  









.. toctree::
    :maxdepth: 2




.. toctree::
    :maxdepth: 2
