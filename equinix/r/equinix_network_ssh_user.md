# equinix_network_ssh_user

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_ssh_user" {
  source = "./modules/equinix/r/equinix_network_ssh_user"

  # device_ids - (required) is a type of set of string
  device_ids = []
  # password - (required) is a type of string
  password = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "device_ids" {
  description = "(required) - list of device identifiers to which user will have access"
  type        = set(string)
}

variable "password" {
  description = "(required) - SSH user password"
  type        = string
}

variable "username" {
  description = "(required) - SSH user login name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "equinix_network_ssh_user" "this" {
  device_ids = var.device_ids
  password   = var.password
  username   = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = equinix_network_ssh_user.this.id
}

output "uuid" {
  description = "returns a string"
  value       = equinix_network_ssh_user.this.uuid
}

output "this" {
  value = equinix_network_ssh_user.this
}
```

[top](#index)