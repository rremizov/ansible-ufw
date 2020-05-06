.. sectnum::

UFW
===

Install Uncomplicated Firewall and configure rules.

Features
--------

- Default policy to deny all incoming connections (except SSH port).

Requirements
------------

- Debian

Role Vars
---------

``ufw_rules``
~~~~~~~~~~~~~

A list of UFW rules. Each rule's parameters are passed to the `ufw`_ module as-is.

Example
-------

.. code:: yaml

    ufw_rules:
      - comment: "Expose http port."
        rule: "allow"
        port: 80
        direction: "in"
        from: "any"
        proto: "tcp"
      - comment: "Expose https port."
        rule: "allow"
        port: 443
        direction: "in"
        from: "any"
        proto: "tcp"

.. _ufw:: https://docs.ansible.com/ansible/latest/modules/ufw_module.html
