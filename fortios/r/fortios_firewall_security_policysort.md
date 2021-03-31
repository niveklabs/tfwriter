# fortios_firewall_security_policysort

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_security_policysort" {
  source = "./modules/fortios/r/fortios_firewall_security_policysort"

  # comment - (optional) is a type of string
  comment = null
  # force_recreate - (optional) is a type of string
  force_recreate = null
  # sortby - (required) is a type of string
  sortby = null
  # sortdirection - (required) is a type of string
  sortdirection = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_recreate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sortby" {
  description = "(required)"
  type        = string
}

variable "sortdirection" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_security_policysort" "this" {
  comment        = var.comment
  force_recreate = var.force_recreate
  sortby         = var.sortby
  sortdirection  = var.sortdirection
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_security_policysort.this.id
}

output "state_policy_list" {
  description = "returns a list of object"
  value       = fortios_firewall_security_policysort.this.state_policy_list
}

output "this" {
  value = fortios_firewall_security_policysort.this
}
```

[top](#index)