# Go Ansible Role

Installs Golang

## Requirements

This role requires Ansible 2.0 or higher.

## Role Variables

### Defaults

    - name: go_version
      desc: Target go version for installation
      value: '1.8.1'


### Vars

These are not meant to be modified

    - name: go_tarball
      desc: Name of go archive
      value: 'go{{ go_version }}.linux-amd64.tar.gz'

    - name: go_download_url
      desc: URL for downloading go tarball
      value: 'https://storage.googleapis.com/golang/{{ go_tarball }}'

    - name: go_download_dir
      desc: Target directory for tarball download
      value: '/usr/local/src/{{ go_tarball }}'

    - name: go_install_dir
      desc: Install location for go artifacts
      value: '/usr/local/go'

    - name: go_binary_path
      desc: Full path for go binary
      value: '/usr/local/go/bin/go'


## Dependencies

None

## Example Playbook

Install go language

    - hosts: all
      roles:
        - ansible-role-go

## Testing

Tests can be executed with local vagrantfile using the command. This mounts the role directory in the guest and executes the role via the playbook in `tests/` folder.

```shell
vagrant up
```
