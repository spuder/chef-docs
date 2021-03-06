.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

This resource has the following attributes:


enable_checkout
OLD: Use to check out a repo from master.
NEW: 


.. list-table::
   :widths: 150 450
   :header-rows: 1

   * - Attribute
     - Description
   * - ``additional_remotes``
     - |additional_remotes|
   * - ``checkout_branch``
     - |checkout_branch git| See ``revision``. Default value: ``deploy``.
   * - ``depth``
     - |depth git_shallow_clone| The default behavior will do a full clone.
   * - ``destination``
     - |destination resource scm| Default value: the ``name`` of the resource block. |see syntax|
   * - ``enable_checkout``
     - |enable_git_checkout| Set to ``false`` when using the ``checkout_branch`` attribute to prevent the |resource scm_git| resource from attempting to check out master from master. Default value: ``true``.
   * - ``enable_submodules``
     - |enable_submodules| Default value: ``false``.
   * - ``environment``
     - |environment variables|

       .. note:: The |resource scm_git| provider automatically sets the ``ENV['HOME']`` and ``ENV['GIT_SSH']`` environment variables. To override this behavior and provide different values, add ``ENV['HOME']`` and/or ``ENV['GIT_SSH']`` to the ``environment`` |ruby hash|.
   * - ``group``
     - |group deploy|
   * - ``provider``
     - Optional. |provider resource_parameter|
   * - ``reference``
     - |reference resource scm|
   * - ``remote``
     - |remote resource|
   * - ``repository``
     - |uri repository_git|
   * - ``revision``
     - |revision| See ``checkout_branch``. Default value: ``HEAD``.

       .. include:: ../../includes_resources/includes_resource_scm_git_attributes_revision.rst
   * - ``ssh_wrapper``
     - |ssh_wrapper resource|
   * - ``timeout``
     - |timeout scm| |timeout scm_value_git|
   * - ``user``
     - |user checked_out_code| Default value: the home directory of this user, as indicated by the ``HOME`` environment variable.
