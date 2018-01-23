.. _users-management:

.. index::
   single: User Management

***************************************************
Users Management
***************************************************

.. index::
   single: Add User

.. _add-new-user:

Add a new user
---------------

To add a new user to Entando follow this procedure:

From Users Settings >> Users

* Click the Add button
* Provide Username
* Provide Password
* Confirm Password
* Choose a profile Type
* Set the status to ON (OFF is set by default)


.. note::
 
 Note that a user profile type is mandatory, then at least one user profile type must already been present in the system to be able to add a new user, that's the case in a new Entando installation where at the least the "Default User Profile" is always present. 

What a user can see or do on Entando is governed by the user groups to which he belongs and by the user roles he has assigned.
That is managed by editing the user authorizations, please refer to user-authorizations_.


:ref:`figure35`


.. _user-authorizations:

Managing user authorizations
-----------------------------

From Users Settings >> Users

* Select Manage Authorizations from the kebab menu
* Assign User Group
* Assign a User Role
* Click Add

:ref:`figure32`

.. Note:

A user may have multiple roles.
But at least a role must be assigned to let the user login.

.. _add-user-roles:

Users Roles
-------------------

A user role defines the permissions a user has in accessing Entando platform pages contents and actions, available permissions are:

-  Content Editing

-  User Profile Editing

-  User Editing

-  Access to Administration Area

-  Operations on Categories

-  Operations on Pages

-  Operations on Resources

-  View Users and Profiles

-  Supervision of Contents

-  All functions

Each permission represents an action the user can perform on the system, but those actions refer only to the pages, contents and resources that are in the group to which the user belongs.

Example.
Let's suppose that the user1 belongs to group1 and has the role1 with permissions of: Operations on Pages, Content Editing and Access to Administration Area.
In this case the user1 will have access to the Page Designer section because has the permission Operations on Pages but will have rights only on the pages owned by group1 or group joined, at the same time will have access to Contents because has the  permission of Content Editing but will have rights only on the contents owned by group1 or group joined. The permission to Access to Administration Area is needed because any configuration is done from backend.

Summarizing then the group defines what a user has access to, while the role defines what a user can do on the resources to which he has access.




