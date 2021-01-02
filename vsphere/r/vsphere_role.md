# vsphere_role

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_role" {
  source = "./modules/vsphere/r/vsphere_role"

  # name - (required) is a type of string
  name = null
  # role_privileges - (optional) is a type of list of string
  role_privileges = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the storage policy."
  type        = string
}

variable "role_privileges" {
  description = "(optional) - The privileges to be associated with the role."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_role" "this" {
  name            = var.name
  role_privileges = var.role_privileges
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_role.this.id
}

output "label" {
  description = "returns a string"
  value       = vsphere_role.this.label
}

output "this" {
  value = vsphere_role.this
}
```

[top](#index)