Ansible role: vim
=========

![Build & Deploy](https://github.com/Provizanta/ansible-role-vim/workflows/molecule/badge.svg?branch=master)

Install and configure vim or its flavors (e.g. nvim). Use a specific plugin manager - only 'vundle' is supported at the moment.

Requirements
------------

None

Role Variables
--------------

These variables are set in [defaults/main.yml](./defaults/main.yml):

    vim_flavor: vim   # vim|vim-gtk3|nvim

    vim_plugin_manager: vundle

These variables do not have default values and can be set:

    vim_configuration:
      - name: <string, configuration block name>
        block: <string, configuration blocks as multi-line text>
    vim_plugins:
      - name: <string, plugin name>
        settings: <string, settings as multi-line text>

Dependencies
------------

None

Example Playbook
----------------

    - name: Converge
      hosts: all
      roles:
        - role: vim
          vars:
            vim_configuration:
              - name: configuration block title
                block: |
                  set clipboard=unnamed
                  set backspace=indent,eol,start
            vim_plugin_manager: vundle
            vim_plugins:
              - name: 'vim-scripts/vim-auto-save'
                settings: |
                  let g:auto_save=1
                  let g:auto_save_in_insert_mode=0
                  let g:auto_save_no_updatetime=5

License
-------

MIT

Author Information
------------------

Tibor Csóka
