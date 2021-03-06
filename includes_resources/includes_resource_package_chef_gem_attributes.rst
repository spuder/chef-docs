.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

This resource has the following attributes:

.. list-table::
   :widths: 150 450
   :header-rows: 1

   * - Attribute
     - Description
   * - ``clear_sources``
     - |clear_sources| Default value: ``false``.

       .. note:: Another approach is to use the |resource package_gem| resource, and then specify the ``gem_binary`` location to the |rubygems| directory that is used by |chef|. For example:

          .. code-block:: ruby

             gem_package 'package' do
               gem_binary Chef::Util::PathHelper.join(Chef::Config.embedded_dir,'bin','gem')
               action :install             
             end

   * - ``compile_time``
     - |chef_gem compile_time| Recommended value: ``false``. The |chef client| will emit a warning when this setting is ``true``. Use a ``respond_to?`` check to ensure backward compatibility. For example:

       .. code-block:: ruby

          chef_gem 'aws-sdk' do
            compile_time false if respond_to?(:compile_time)
          end

       .. warning:: If you are using ``chef-sugar``---a `community cookbook <https://supermarket.chef.io/cookbooks/chef-sugar>`__---it must be version 3.0.1 (or higher) to use the previous example. If you are using an older version of ``chef-sugar``, the following workaround is required:

          .. code-block:: ruby

             chef_gem 'gem_name' do
               compile_time true if Chef::Resource::ChefGem.instance_methods(false).include?(:compile_time)
             end

          See this `blog post <http://jtimberman.housepub.org/blog/2015/03/20/chef-gem-compile-time-compatibility/>`__ for more background on this behavior.
   * - ``options``
     - |command options|
   * - ``package_name``
     - |name package| Default value: the ``name`` of the resource block. |see syntax|
   * - ``provider``
     - Optional. |provider resource_parameter| |see providers|
   * - ``source``
     - Optional. |source resource package|
   * - ``timeout``
     - |timeout|
   * - ``version``
     - |version package|


