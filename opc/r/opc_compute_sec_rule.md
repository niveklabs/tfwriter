# opc_compute_sec_rule

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_sec_rule" {
  source = "./modules/opc/r/opc_compute_sec_rule"

  # action - (required) is a type of string
  action = null
  # application - (required) is a type of string
  application = null
  # description - (optional) is a type of string
  description = null
  # destination_list - (required) is a type of string
  destination_list = null
  # disabled - (optional) is a type of bool
  disabled = null
  # name - (required) is a type of string
  name = null
  # source_list - (required) is a type of string
  source_list = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "application" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_list" {
  description = "(required)"
  type        = string
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "source_list" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_sec_rule" "this" {
  # action - (required) is a type of string
  action = var.action
  # application - (required) is a type of string
  application = var.application
  # description - (optional) is a type of string
  description = var.description
  # destination_list - (required) is a type of string
  destination_list = var.destination_list
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # name - (required) is a type of string
  name = var.name
  # source_list - (required) is a type of string
  source_list = var.source_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_sec_rule.this.id
}

output "this" {
  value = opc_compute_sec_rule.this
}
```

[top](#index)