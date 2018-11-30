Vim
=========

Vim editor setup.

Requirements
------------

None

Role Variables
--------------

    plugin_manager: <used plugin manager, default: vundle>
    plugins: <list of plugins>
      - name: <plugin name>


Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: keepass
          vars:
            plugin_manager: vundle
            plugins:
              - name: 'WhoeverItIs/HisPlugin'


License
-------

MIT

Author Information
------------------

Tibor Csoka
