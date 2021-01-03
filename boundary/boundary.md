# boundary

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "boundary" {
  version = "0.1.0"

  # addr - (required) is a type of string
  addr = null
  # auth_method_id - (optional) is a type of string
  auth_method_id = null
  # password_auth_method_login_name - (optional) is a type of string
  password_auth_method_login_name = null
  # password_auth_method_password - (optional) is a type of string
  password_auth_method_password = null
  # recovery_kms_hcl - (optional) is a type of string
  recovery_kms_hcl = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [boundary_account](./r/boundary_account.md)

- [boundary_auth_method](./r/boundary_auth_method.md)

- [boundary_group](./r/boundary_group.md)

- [boundary_host](./r/boundary_host.md)

- [boundary_host_catalog](./r/boundary_host_catalog.md)

- [boundary_host_set](./r/boundary_host_set.md)

- [boundary_role](./r/boundary_role.md)

- [boundary_scope](./r/boundary_scope.md)

- [boundary_target](./r/boundary_target.md)

- [boundary_user](./r/boundary_user.md)


[top](#index)

### Datasources



[top](#index)