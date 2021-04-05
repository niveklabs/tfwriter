# opsgenie_custom_role

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_custom_role" {
  source = "./modules/opsgenie/r/opsgenie_custom_role"

  # disallowed_rights - (optional) is a type of set of string
  disallowed_rights = []
  # extended_role - (optional) is a type of string
  extended_role = null
  # granted_rights - (optional) is a type of set of string
  granted_rights = []
  # role_name - (required) is a type of string
  role_name = null
}
```

[top](#index)

### Variables

```terraform
variable "disallowed_rights" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "extended_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "granted_rights" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "role_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_custom_role" "this" {
  disallowed_rights = var.disallowed_rights
  extended_role     = var.extended_role
  granted_rights    = var.granted_rights
  role_name         = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_custom_role.this.id
}

output "this" {
  value = opsgenie_custom_role.this
}
```

[top](#index)