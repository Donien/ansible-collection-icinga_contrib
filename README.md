# Ansible Collection - netways.icinga_contrib

This Collection is meant to be an addition to the official [Ansible Collection by Icinga](https://github.com/Icinga/ansible-collection-icinga/).  
Since Icinga's Collection currently only handles official Icinga components, **netways.icinga_contrib** aims to fill the gap.

For example, there are Icinga Web 2 modules provided by the community which are used a lot like the [Grafana module](https://github.com/Mikesch-mp/icingaweb2-module-grafana) or the [Map module](https://github.com/nbuchwitz/icingaweb2-module-map).  
This Collection is meant to handle such cases.

Since NETWAYS maintains this Collection contributions are evaluated on a case-by-case basis. See [Contributing](#Contributing).

## Installing the Collection

**Ansible Galaxy**  
To install the Collection from Ansible Galaxy:

```
ansible-galaxy collection install netways.icinga_contrib
```

**Git**  
To install the Collection's main branch from this repository:

```
ansible-galaxy collection install git+https://github.com/netways/ansible-collection-icinga_contrib,main
```

To install a specific tag release:

```
ansible-galaxy collection install git+https://github.com/netways/ansible-collection-icinga_contrib,1.2.3
```

## Using the Collection

To use the collection specify the FQCN of the module, plugin or role you want to use.

```yaml
- name: Run role netways.icinga_contrib.icingaweb2_modules
  hosts: somehost

  vars:
    icingaweb2_modules:
      grafana:
        ...

  roles:
    - netways.icinga_contrib.icingaweb2_modules
```

## Roles

- **[netways.icinga_contrib.icingaweb2_modules](./roles/icingaweb2_modules/README.md)**  
  This role is used to manage modules for Icinga Web 2 not managed by Icinga's official Collection.

## Contributing

Contributions are welcome!

Since maintaining this repository is work we might reject certain contributions or feature requests.  
We also need to have a certain level of trust when it comes to third party code, e.g. Icinga Web 2 modules.  
Decisions are made on a case-by-case basis.

If you want to know whether a certain new feautre would be welcome, feel free to simply ask and start a discussion.

Also, if you want to contribute to this Collection, please follow these general guidelines.

### Issues

- Open issues. The more we know the better we can maintain this Collection.
- If you want to work on an open issue, let us know so we can assign it to you and keep track.
- Request new features via an issue.
- If applicable, use one of the provided issue templates.
- Be precise when describing bugs / feature requests.

### Pull Requests

- Link related issues, especially ones closed by the PR.
- Make sure to provide changelog fragments describing the changes within your PR. For more information see [antsibull-changelog](https://ansible.readthedocs.io/projects/antsibull-changelog/changelogs/).
- If you introduce or change variables, add them to the appropriate README file.
- The Collection is tested using [Molecule](https://ansible.readthedocs.io/projects/molecule/). If introducing new code, you should also provide new tests if you can.

## License

GPL-3.0-only
