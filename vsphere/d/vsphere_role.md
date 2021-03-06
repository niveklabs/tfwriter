# vsphere_role

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_role" {
  source = "./modules/vsphere/d/vsphere_role"

  # description - (optional) is a type of string
  description = null
  # label - (required) is a type of string
  label = null
  # name - (optional) is a type of string
  name = null
  # role_privileges - (optional) is a type of list of string
  role_privileges = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the role."
  type        = string
  default     = null
}

variable "label" {
  description = "(required) - The display label of the role."
  type        = string
}

variable "name" {
  description = "(optional) - Name of the role."
  type        = string
  default     = null
}

variable "role_privileges" {
  description = "(optional) - Privileges to be associated with the role"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_role" "this" {
  # description - (optional) is a type of string
  description = var.description
  # label - (required) is a type of string
  label = var.label
  # name - (optional) is a type of string
  name = var.name
  # role_privileges - (optional) is a type of list of string
  role_privileges = var.role_privileges
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_role.this.id
}

output "this" {
  value = vsphere_role.this
}
```

[top](#index)