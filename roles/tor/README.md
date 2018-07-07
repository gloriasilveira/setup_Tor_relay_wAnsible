Role Name
=========

This role installs and configures the Tor relay software on a box so that it can become a Tor relay/node in the Tor distributed network. Once the relay is configured, it will also backup and store locally on the Ansible control box a .tgz of each relay's keys, and will go out and dynamically gather the fingerprints of all your relays and update the torrc MyFamily config line with these fingerprints.

Role Variables
--------------

There are two variables this role takes: relay_name, which is what you want your relay's name to be when it shows up on the Tor network, and contact_email, the email address you want to publish as the relay operator's contact address.

License
-------

BSD

Author Information
------------------

Gloria Silveira (www.gloriasilveira.com)
