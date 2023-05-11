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

    vim_configuration:      # string, contents of the .vimrc file


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
            vim_plugin_manager: vundle
            vim_configuration: |
              " VUNDLE START
              set nocompatible     " be iMproved, required (vundle)
              filetype off         " required (vundle), turns off filetype

              if has('nvim')
                  let s:editor_root=expand("~/.config/nvim/")
              else
                  let s:editor_root=expand("~/.vim/")
              endif

              " set the runtime path to include Vundle and initialize
              " set rtp+=~/.config/nvim//bundle/vundle
              let &rtp = &rtp . ',' . s:editor_root . '/bundle/vundle/'

              call vundle#begin(s:editor_root . '/bundle')

              Plugin 'VundleVim/Vundle.vim' " let Vundle manage Vundle, required

              " custom plugins
              Plugin 'editorconfig/editorconfig-vim'
              Plugin 'vim-scripts/vim-auto-save'

              call vundle#end()
              filetype plugin indent on    " required (vundle) - turns on filetype
              " VUNDLE END

              " GENERIC CONFIGURATION
              " basic configuration
              set viminfo=
              set updatetime=200

              " PLUGIN CONFIGURATION
              " plugin vim-scripts/vim-auto-save
              let g:auto_save=1
              let g:auto_save_in_insert_mode=0
              let g:auto_save_no_updatetime=5

License
-------

MIT

Author Information
------------------

Tibor Csóka
