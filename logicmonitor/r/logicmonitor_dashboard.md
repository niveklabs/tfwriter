# logicmonitor_dashboard

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
module "logicmonitor_dashboard" {
  source = "./modules/logicmonitor/r/logicmonitor_dashboard"

  # description - (optional) is a type of string
  description = null
  # group_id - (optional) is a type of number
  group_id = null
  # name - (required) is a type of string
  name = null
  # public - (optional) is a type of bool
  public = null
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

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public" {
  description = "(optional)"
  type        = bool
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
resource "logicmonitor_dashboard" "this" {
  # description - (optional) is a type of string
  description = var.description
  # group_id - (optional) is a type of number
  group_id = var.group_id
  # name - (required) is a type of string
  name = var.name
  # public - (optional) is a type of bool
  public = var.public
  # template - (optional) is a type of string
  template = var.template
  # widget_tokens - (optional) is a type of map of string
  widget_tokens = var.widget_tokens
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_dashboard.this.id
}

output "this" {
  value = logicmonitor_dashboard.this
}
```

[top](#index)