# logicmonitor_collector_group

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
module "logicmonitor_collector_group" {
  source = "./modules/logicmonitor/r/logicmonitor_collector_group"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # properties - (optional) is a type of map of string
  properties = {}
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "logicmonitor_collector_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # properties - (optional) is a type of map of string
  properties = var.properties
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_collector_group.this.id
}

output "this" {
  value = logicmonitor_collector_group.this
}
```

[top](#index)