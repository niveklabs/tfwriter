# ovh_me_ssh_key

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
module "ovh_me_ssh_key" {
  source = "./modules/ovh/d/ovh_me_ssh_key"

  # key_name - (required) is a type of string
  key_name = null
}
```

[top](#index)

### Variables

```terraform
variable "key_name" {
  description = "(required) - Name of this public Ssh key"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_ssh_key" "this" {
  key_name = var.key_name
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = data.ovh_me_ssh_key.this.default
}

output "id" {
  description = "returns a string"
  value       = data.ovh_me_ssh_key.this.id
}

output "key" {
  description = "returns a string"
  value       = data.ovh_me_ssh_key.this.key
}

output "this" {
  value = ovh_me_ssh_key.this
}
```

[top](#index)