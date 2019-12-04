mariadb_box
===========

Underlying ansible roles: `sa-mariadb`.  Check roles documentation for whole set of parameters to override.

Supported tags:

`sa_mariadb`

Supported parameters overrides:


```
```


Using with vagrant boilerplate (https://github.com/Voronenko/devops-vagrant-ansible-boilerplate)

```

    config.vm.provision "mariadb-box", type: "ansible" do |ansible|
        ansible.playbook = "deployment/provisioners/mariadb_box/playbook.yml"
        ansible.galaxy_role_file = "deployment/provisioners/mariadb_box/requirements.yml"
        ansible.galaxy_roles_path = "deployment/provisioners/mariadb_box/roles"
        ansible.verbose = true
        ansible.groups = {
            "mysql_box" => [vconfig['vagrant_machine_name']]
        }
        # ansible.tags = ["sa_mysql"]
        ansible.extra_vars = {
            box_provider: "vagrant",
            env: "vagrant"
        }
    end


```
