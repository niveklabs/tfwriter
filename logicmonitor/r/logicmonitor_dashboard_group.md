# logicmonitor_dashboard_group

[back](../logicmonitor.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    logicmonitor = ">= 1.3.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "logicmonitor_dashboard_group" {
  source = "./modules/logicmonitor/r/logicmonitor_dashboard_group"

  # description - (optional) is a type of string
  description = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of number
  parent_id = null
  # template - (optional) is a type of string
  template = null
  # widget_tokens - (optional) is a type of map of string
  widget_tokens = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "widget_tokens" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "logicmonitor_dashboard_group" "this" {
  description   = var.description
  force_delete  = var.force_delete
  name          = var.name
  parent_id     = var.parent_id
  template      = var.template
  widget_tokens = var.widget_tokens
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_dashboard_group.this.id
}

output "this" {
  value = logicmonitor_dashboard_group.this
}
```

[top](#index)