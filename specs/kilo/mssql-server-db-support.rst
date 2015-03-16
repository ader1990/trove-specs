..
   This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

 Sections of this template were taken directly from the Nova spec
 template at:
 https://github.com/openstack/nova-specs/blob/master/specs/template.rst
..

=======================================
 Microsoft SQL Server Datastore support
=======================================

https://blueprints.launchpad.net/trove/+spec/mssql-server-support

Microsoft SQL Server is a proven, predictable performance database server, provided by Microsoft.
As Trove aims to become a production DBaaS, its abilities should comprise also Microsoft database
technology.

See more information at::

 http://www.microsoft.com/en-us/server-cloud/products/sql-server/

Problem description
===================

In order to meet the users' need in OpenStack, Trove should support Microsoft SQL Server.

Proposed change
===============

For the initial implementation, Microsoft SQL Server will support minimum working cases and gradually
acquire full compatibility.

With respect to datastore compatibility matrix, Microsoft SQL Server support will include(regular)::

     launch
     reboot
     terminate
     terminate
     resize
     backup
     restore
     clustering
     users API
     databases API
     root API
     replication

To support Microsoft SQL Server by Trove, the following changes will be added::

    "guestagent manager" - handles deployment and management of Microsoft SQL Server instance
    "backup strategy" - handles backuping/restoring procedure for Microsoft SQL Server
    "replication strategy" - handles replication procedure for Microsoft SQL Server
    "storage strategy" - handles storage procedure for Microsoft SQL Server

The following Microsoft SQL Server versions will be supported::

 Versions: 2012,2014
 Editions: Express, Web, Standard, Enterprise
 
Some features will be limited by the actual edition limitations.
 
Configuration
-------------

Each datastore requires its own configuration group. Next options should be added to cover needed configurations::

     tcp_ports
     upd_ports
     mount_point
     usage_timeout
     volume_support
     device_path

Database
--------

None

Public API
----------

None

Public API Security
-------------------

None

Internal API
------------

None

Guest Agent
-----------

Add support to the Guest Agent for the following Windows versions::

    Windows Server 2008 R2
    Windows Server 2012
    Windows Server 2012 R2
    Windows 8
    Windows 8.1

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee::

  Launchpad: avladu
  
  IRC: avladu
  
  Email: avladu@cloudbasesolutions.com

Milestones
----------

 Liberty

Work Items
----------

List of items to develop::

 DIB elements development
 guestagent manager development
 backup/restore feature development
 replication feature development
 storage feature development

Upgrade Implications
====================

None

Dependencies
============

None

Testing
=======

Microsoft SQL Server support will include::

 unit testing
 integration testing

Continuous integration testing will be provided by the Microsoft Hyper-V CI.

Documentation Impact
====================

None

References
==========

Microsoft SQL Server documentation https://msdn.microsoft.com/en-us/library/bb545450.aspx

