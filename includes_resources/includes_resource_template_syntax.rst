.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.


A |resource template| resource block typically declares the location in which a file is to be created, the source template that will be used to create the file, and the permissions needed on that file. For example:

.. code-block:: ruby

   template '/etc/chef/server.rb' do
     source 'server.rb.erb'
     owner 'root'
     group 'root'
     mode '00644'
   end

where

* ``'/etc/chef/server.rb'`` specifies the location in which the file is created
* ``'server.rb.erb'`` specifies the name of a template that exists in in the ``/templates`` folder of a cookbook
* ``owner``, ``group``, and ``mode`` define the permissions

The full syntax for all of the attributes that are available to the |resource template| resource is:

.. code-block:: ruby

   template 'name' do
     atomic_update              true
     backup                     integer
     cookbook                   'string'
     force_unlink               false
     group                      'string'
     helper(:method)            { "string"} # see Helpers below
     helpers(module)            # see Helpers below
     inherits                   true
     local                      false
     manage_symlink_source nil  # can be true or false
     mode                       'string'
     owner                      'string'
     path                       'string'  # defaults to 'name' if not specified
     provider                   Chef::Provider::File::Template
     rights                     Hash
     sensitive                  false
     source                     'string' or [ array ]  # filename.erb
     variables                  Hash
     verify                     'string' or :symbol
     action                     :action
   end

where 

* ``template`` is the resource
* ``name`` is the name of the resource block, typically the path to the location in which a file is created *and also* the name of the file to be managed. For example: ``/var/www/html/index.html``, where ``/var/www/html/`` is the fully qualified path to the location and ``index.html`` is the name of the file
* ``source`` is the template file that will be used to create the file on the node, for example: ``index.html.erb``; the template file is located in the ``/templates`` directory of a cookbook
* ``:action`` identifies the steps the |chef client| will take to bring the node into the desired state
* ``atomic_update``, ``backup``, ``cookbook``, ``force_unlink``, ``group``, ``helper``, ``helpers``, ``inherits``, ``local``, ``manage_symlink_source``, ``mode``, ``owner``, ``path``, ``provider``, ``rights``, ``sensitive``, ``source``, ``variables``, and ``verify`` are attributes of this resource, with example values shown. |see attributes|
