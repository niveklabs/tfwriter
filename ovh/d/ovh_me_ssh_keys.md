# ovh_me_ssh_keys

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
module "ovh_me_ssh_keys" {
  source = "./modules/ovh/d/ovh_me_ssh_keys"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "ovh_me_ssh_keys" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_me_ssh_keys.this.id
}

output "names" {
  description = "returns a set of string"
  value       = data.ovh_me_ssh_keys.this.names
}

output "this" {
  value = ovh_me_ssh_keys.this
}
```

[top](#index)