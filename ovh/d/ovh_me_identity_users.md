# ovh_me_identity_users

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_identity_users" {
  source = "./modules/ovh/d/ovh_me_identity_users"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "ovh_me_identity_users" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_me_identity_users.this.id
}

output "users" {
  description = "returns a set of string"
  value       = data.ovh_me_identity_users.this.users
}

output "this" {
  value = ovh_me_identity_users.this
}
```

[top](#index)