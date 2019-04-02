Vim
=========

Vim editor setup.

Requirements
------------

None

Role Variables
--------------

    flavor: <vim flavor to be used, vim|nvim>
    plugin_manager: <used plugin manager, default: vundle>
    configuration:
      - name:
        block: <configuration blocks as multi-line text> 
    plugins: 
      - name: <plugin name>
        settings: <string< settings multi-line text

Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: vim
          vars:
            configuration:
              - name: configuration block title
                block: |
                  set clipboard=unnamed
                  set backspace=indent,eol,start
            plugin_manager: vundle
            plugins:
              - name: 'WhoeverItIs/HisPlugin'
                settings: |
                  set value         " nicely formatted string


License
-------

MIT

Author Information
------------------

Tibor Csoka
