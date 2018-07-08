# setup_Tor_relay_wAnsible

This repo contains Ansible roles and a playbook to set up and manage a Tor Relay node.

This will set up a non-exit relay by taking a standard EC2 instance you've spun up and tagged, and installing NTP on it, setting up a crontab to do automatic updates each night at 2am, installing the tor relay software, configuring it, and then outputting to you the fingerprints of your resulting tor nodes. 

If you are setting up multiple EC2 instances, Ansible will know this and will also dynamically grab the fingerprints of each relay and insert this information into the torrc MyFamily configuration.

To run this playbook, here is a high-level idea of what to do, but for best results, please use the tutorial here: http://gloriasilveira.com/how-to-set-up-an-ec2-tor-relay-with-ansible.html 

1-Launch your ec2 instance/instances on AWS and tag them with the tag "Purpose: TorRelay". 

2-Execute the following command from your Ansible control box (NOT the relay instances themselves):

AWS_PROFILE=default ansible-playbook -i ec2.py ./setup_Tor_relay_wAnsible/setup_tor_node.yml --private-key=KEYHERE -u ec2-user -e "relay_name=NAMEHERE contact_email=EMAILHERE"

Making sure to edit the extra-vars section (what starts with "e") to have your contact email and whatever you want to name your relay/relays in there.

3-Ansible will then go out, take whatever instances it finds in your AWS account tagged as "Purpose: TorRelay" and will begin installing and configuring Tor on them. Once Ansible finishes, it backs up each relays private keys to your local Ansible box, and grabs the fingerprint for each node and then updates your torrc MyFamily line with this info.
