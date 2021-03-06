# aci_lacp_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_lacp_policy" {
  source = "./modules/aci/r/aci_lacp_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # ctrl - (optional) is a type of list of string
  ctrl = []
  # description - (optional) is a type of string
  description = null
  # max_links - (optional) is a type of string
  max_links = null
  # min_links - (optional) is a type of string
  min_links = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ctrl" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_links" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_links" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_lacp_policy" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # ctrl - (optional) is a type of list of string
  ctrl = var.ctrl
  # description - (optional) is a type of string
  description = var.description
  # max_links - (optional) is a type of string
  max_links = var.max_links
  # min_links - (optional) is a type of string
  min_links = var.min_links
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "ctrl" {
  description = "returns a list of string"
  value       = aci_lacp_policy.this.ctrl
}

output "description" {
  description = "returns a string"
  value       = aci_lacp_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_lacp_policy.this.id
}

output "max_links" {
  description = "returns a string"
  value       = aci_lacp_policy.this.max_links
}

output "min_links" {
  description = "returns a string"
  value       = aci_lacp_policy.this.min_links
}

output "mode" {
  description = "returns a string"
  value       = aci_lacp_policy.this.mode
}

output "name_alias" {
  description = "returns a string"
  value       = aci_lacp_policy.this.name_alias
}

output "this" {
  value = aci_lacp_policy.this
}
```

[top](#index)