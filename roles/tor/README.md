Role Name
=========

This role installs and configures the Tor relay software on a box so that it can become a Tor relay/node in the Tor distributed network.

Role Variables
--------------

There are two variables this role takes: relay_name, which is what you want your relay's name to be when it shows up on the Tor network, and contact_email, the email address you want to publish as the relay operator's contact address.
Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

Gloria Silveira (www.gloriasilveira.com)
