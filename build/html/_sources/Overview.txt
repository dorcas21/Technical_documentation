Overview
==========


The purpose of this project is to establish an hierarchy of the drugs supply chain
that is not captured in DHIS2 for purposes of analysis and report generation.

As things stand, the Kenya instance of `DHIS2`_ only establishes a hierarchy based on 
the countries administrative units which while important, does not capture the
supply chain hierarchy.

The drug supply hierarchy needs to place facilities in their correct order clearly
showing the reporting chain ie what facilities report to what and what facilities
are children so to speak of what facilities.


Facility types
----------------

For ART-related medicines, the health facilities are categorized into five (5) types:

    #. Central stores
    #. Central store dispensing points
    #. Satellite stores
    #. Stand alone sites
    #. Sub-County stores (formerly the district stores)


For Nutrition & HIV commodities, the health facilities are categorized into four (4) types:

    #. Central sites 
    #. Central site Dispensing points 
    #. Satellite sites 
    #. Standalone sites    


The reporting hierachy
----------------------

The Standalone sites, Sub-county Stores and the Central sites form the **ORDERING POINTS**. These Ordering points are supplied by the national/central level stores, e.g. `KEMSA`_. An Ordering point is defined as a designated Central site, Standalone site or a Sub-county store that orders ARV and OI commodities from the allocated commodity pipeline, e.g. `KEMSA`_, `NHPplus`_. Usually these are higher level facilities, e.g. hospitals.

A **Central site** is defined as a facility that provides ART/Nutrition services and also supplies lower level sites (Satellite sites) with ART-related medicines & nutrition commodities. 

As an Ordering point, Central sites own (in the reporting hierarchy) the Central site Dispensing points and the Satellite sites.



A **Central site Dispensing point** is the Central site itself reporting for its own commodity stock and usage (without that of the Satellite sites), as a service delivery point. 




**Satellite sites** are health facilities that report to the Central stores, i.e. that are health facilities providing ART/Nutrition & HIV services, that are supplied with commodities by a Central site or Sub-county store.  

Usually these are lower level health facilities, e.g. health centres, dispensaries.


A **Sub-county store** is defined as a facility that DOES NOT provide ART/Nutrition & HIV services but supplies lower level sites (Satellite sites) with ART-related medicines and Nutrition & HIV commodities.



A **Standalone site**, as the name suggests, do not have any affiliation in the reporting hierarchy, i.e. they are facilities that provide ART/Nutrition & HIV services but DO NOT supply any lower level sites (Satellite sites). 



Existing facilities (Level 4) are used as stores for the purpose of drug dispensing.

These facilities are captures in DHIS2 as Level 4 Organization Units and thus no hierarchy exists between them.

The purpose of this project is to establish that hierarchy.




.. note::

    * `NASCOP`_ maintains the list of approved Central, Satellite and Standalone sites, and Sub-County stores.

    * Each Central site and Sub-county store has a defined list of Satellite sites. 
    * No Satellite site should report or receive stocks from more than one (1) Central site or Sub-county store.




.. _`NASCOP`: http://nascop.or.ke/

.. _`KEMSA`: http://www.kemsa.co.ke/

.. _`NHPplus`: https://www.fbo.gov/index?s=opportunity&mode=form&id=7ff3aa1c240558fcfe5cfc118e1bddbf&tab=core&_cview=1

.. _`DHIS2`: http://test.hiskenya.org/dhis-web-commons/security/login.action;jsessionid=720CD1B3E45168E4E27916FA020C6887




.. toctree::
    :maxdepth: 2
