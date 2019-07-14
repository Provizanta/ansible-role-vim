Ansible role: vim
=========

[![Build Status](https://travis-ci.com/Provizanta/ansible-role-vim.svg?branch=master)](https://travis-ci.com/Provizanta/ansible-role-vim)

Install and configure vim or its flavors (e.g. nvim). Use a specific plugin manager - only 'vundle' is supported at the moment.

Requirements
------------

None

Role Variables
--------------

These defaults are set in defaults/main.yml:

    flavor: vim   # vim|vim-gtk3|nvim

    plugin_manager: vundle

Non-defaulted variables that can be set:

    configuration:
      - name: <string, configuration block name>
        block: <string, configuration blocks as multi-line text>
    plugins:
      - name: <string, plugin name>
        settings: <string, settings as multi-line text>

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
              - name: 'Valloric/YouCompleteMe'
                setttings: |
                  set encoding=utf-8

License
-------

MIT

Author Information
------------------

Tibor Csóka
