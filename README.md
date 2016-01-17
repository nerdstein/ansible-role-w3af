# Ansible Role: W3AF

[![Build Status](https://travis-ci.org/nerdstein/ansible-role-w3af.svg?branch=master)](https://travis-ci.org/nerdstein/ansible-role-w3af)

Installs W3AF, a web security scanning tool, on any Linux or UNIX system.

By using this Ansible Role, you are automatically accepting W3AF's disclaimer for use.

This enables W3AF's console.

## Requirements

`git` should be installed and working.

`pip` should be installed and working.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    w3af_path: /usr/local/bin/w3af

The path where w3af binary will be located. Should be in your user's `$PATH` so you can run commands simply with `w3af_console` instead of the full path.

    w3af_installed_path: /usr/local/share/w3af

The path where the w3af code base will be installed.

    w3af_keep_updated: false

Set this to `true` to update w3af to the latest release every time the playbook is run.

    w3af_add_to_path: true

If `true` the `vendor/bin` directory inside `w3af_path` will be added to the system's default `$PATH` (for all users).

    pip_executable: pip

The executable name or full path to the PIP executable. This is defaulted to `pip` if you don't override the variable.

    git_executable: git

The executable name or full path to the Git executable. This is defaulted to `git` if you don't override the variable.

    w3af_console_executable: w3af_console

The executable name or full path to the w3af_console executable. This is defaulted to `w3af_console` if you don't override the variable.

## Dependencies

None (but make sure you've installed Git, Python, and PIP; the `geerlingguy.git` and `Stouts.python` role is recommended).

## Example Playbook

    - hosts: servers
      roles:
        - nerdstein.w3af

After the playbook runs, `w3af_console` will be placed in `/usr/local/bin/w3af` (this location is configurable), and will be accessible via normal system accounts.

## License

MIT / BSD

## Author Information

This role was created in 2016 by [Adam Bergstein](http://nerdstein.net/).
