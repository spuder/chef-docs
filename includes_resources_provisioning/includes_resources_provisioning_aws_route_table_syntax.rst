.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

The syntax for using the ``aws_route_table`` driver-specific resource is as follows:

.. code-block:: ruby

   aws_route_table 'name' do
     ignore_route_targets          'string' or [ array ]
     route_table_id                'string'
     routes                        Hash
     virtual_private_gateways      'string' or [ array ]
     vpc                           'string'
   end

where 

* ``aws_route_table`` is the resource
* ``name`` is the name of the resource block and also the name of a route table in |amazon vpc|
* ``routes``, and ``vpc`` are attributes of this resource, with example values shown. |see attributes|

**Example**

.. code-block:: ruby

   aws_route_table 'name' do
     vpc 'ref-vpc'
     routes '0.0.0.0/0' => :internet_gateway
     aws_tags :chef_type => "aws_route_table"
   end
