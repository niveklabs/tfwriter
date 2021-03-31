# constellix_vanity_nameserver

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_vanity_nameserver" {
  source = "./modules/constellix/r/constellix_vanity_nameserver"

  # is_default - (optional) is a type of bool
  is_default = null
  # is_public - (optional) is a type of bool
  is_public = null
  # name - (required) is a type of string
  name = null
  # nameserver_group - (required) is a type of number
  nameserver_group = null
  # nameserver_group_name - (optional) is a type of string
  nameserver_group_name = null
  # nameserver_list_string - (required) is a type of string
  nameserver_list_string = null
}
```

[top](#index)

### Variables

```terraform
variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nameserver_group" {
  description = "(required)"
  type        = number
}

variable "nameserver_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nameserver_list_string" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "constellix_vanity_nameserver" "this" {
  is_default             = var.is_default
  is_public              = var.is_public
  name                   = var.name
  nameserver_group       = var.nameserver_group
  nameserver_group_name  = var.nameserver_group_name
  nameserver_list_string = var.nameserver_list_string
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = constellix_vanity_nameserver.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = constellix_vanity_nameserver.this.is_default
}

output "is_public" {
  description = "returns a bool"
  value       = constellix_vanity_nameserver.this.is_public
}

output "nameserver_group_name" {
  description = "returns a string"
  value       = constellix_vanity_nameserver.this.nameserver_group_name
}

output "this" {
  value = constellix_vanity_nameserver.this
}
```

[top](#index)