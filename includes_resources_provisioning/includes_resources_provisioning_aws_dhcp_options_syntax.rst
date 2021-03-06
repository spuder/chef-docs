.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

The syntax for using the ``aws_dhcp_options`` driver-specific resource is as follows:

.. code-block:: ruby

   aws_dhcp_options 'name' do
     dhcp_options_id               'string'
     domain_name                   'string'
     domain_name_servers           [ array ]
     ntp_servers                   [ array ]
     netbios_name_servers          [ array ]
     netbios_node_type             integer
   end

where 

* ``aws_dhcp_options`` is the resource
* ``name`` is the name of the resource block and also the name of an option set for the |dhcp| protocol
* ``domain_name``, ``domain_name_servers``, ``netbios_name_servers``, ``netbios_node_type``, and ``ntp_servers`` are attributes of this resource, with example values shown. |see attributes|

**Example**

.. code-block:: ruby

   aws_dhcp_options 'name' do
     domain_name          'example.com'
     domain_name_servers  %w(8.8.8.8 8.8.4.4)
     ntp_servers          %w(8.8.8.8 8.8.4.4)
     netbios_name_servers %w(8.8.8.8 8.8.4.4)
     netbios_node_type    2
     aws_tags :chef_type => "aws_dhcp_options"
   end
