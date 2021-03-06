Git
===

[![Build Status](https://travis-ci.org/dirn/ansible-git.svg?branch=master)](https://travis-ci.org/dirn/ansible-git)

An Ansible role to install [Git](http://git-scm.com/).

Requirements
------------

This role works on OS X and Debian-based OSes. If using OS X, make sure you have
[Homebrew](http://brew.sh/) installed before running the role. If you're looking
for a role to handle it for you, check out
[dirn.homebrew](https://github.com/dirn/ansible-homebrew).

Role Variables
--------------

Several variables are available to configure the role.

To set the name of the run commands file that will initialize the related
utilities:

    git_runcom: ~/.bashrc

To control where the related utilities are installed:

    git_utility_root: /usr/local/bin

To control if [gitsh](https://github.com/thoughtbot/gitsh) is installed:

    git_install_gitsh: false
    git_gitsh_version: '0.9'

> `git_gitsh_version` isn't used in OS X since Homebrew is used to manage
> installation.

To control if [hub](https://github.com/github/hub) is installed:

    git_install_hub: false
    git_hub_version: '2.2.0'

> `git_hub_version` isn't used in OS X since Homebrew is used to manage
> installation.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: dirn.git
          git_runcom: ~/.zshrc
          git_install_gitsh: true
          git_install_hub: true

License
-------

MIT

Author Information
------------------

This role was created by [Andy Dirnberger](https://github.com/dirn).
