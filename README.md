# ansible-role-win-fileshares

Role to add/remove Windows fileshares

## Table of content

- [Default Variables](#default-variables)
  - [win_fileshares_add](#win_fileshares_add)
  - [win_fileshares_install_features](#win_fileshares_install_features)
  - [win_fileshares_remove](#win_fileshares_remove)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### win_fileshares_add

List of fileshares to be added. https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_share_module.html

#### Default value

```YAML
win_fileshares_add: []
```

#### Example usage

```YAML
win_fileshares_add:
  - name: hrshare
    caching_mode: "Manual"
    change: "HR-Manager"
    deny: "Ext-Users"
    description: "hr"
    encrypt: false
    full: "Administrators, CEO"
    list: true
    path: 'D:\shares\hr'
    read: "HR-Users"
    rule_action: "set"
  - name: marketingshare
    description: "marketing"
    path: 'C:\shares\marketing'
    list: true
    full: "Everyone"
  - name: $adminshare
    description: "admin"
    path: 'C:\shares\admin'
    list: false
    full: "Administrators"
```

### win_fileshares_install_features

Windows features to be installed

#### Default value

```YAML
win_fileshares_install_features: []
```

#### Example usage

```YAML
win_fileshares_install_features:
  - "FS-FileServer"
  - "FS-DFS-Replication"
```

### win_fileshares_remove

Fileshares to be removed

#### Default value

```YAML
win_fileshares_remove: []
```

#### Example usage

```YAML
win_fileshares_remove:
  - "hrshare"
  - "marketingshare"
  - "$adminshare"
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
