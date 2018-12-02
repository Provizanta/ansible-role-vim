Vim
=========

Vim editor setup.

Requirements
------------

None

Role Variables
--------------

    flavor: <vim flavor to be used>
    plugin_manager: <used plugin manager, default: vundle>
    set:
      value: <key values pair prefixed with set>
      property: <property prefixed with set>
    let: <key value pair prefixed with let>
    other: <a single line to be written to the config file>
    plugins: <list of plugins>
      - name: <plugin name>
        set:
          value: <key values pair prefixed with set>
          property: <property prefixed with set>
        let: <key value pair prefixed with let>
        other: <a single line to be written to the config file>

Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: vim
          vars:
            let:
              key: value
            plugin_manager: vundle
            plugins:
              - name: 'WhoeverItIs/HisPlugin'
                set:
                  key: value


License
-------

MIT

Author Information
------------------

Tibor Csoka
