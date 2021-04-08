# turbot_resource

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_resource" {
  source = "./modules/turbot/r/turbot_resource"

  # akas - (optional) is a type of list of string
  akas = []
  # data - (optional) is a type of string
  data = null
  # full_data - (optional) is a type of string
  full_data = null
  # full_metadata - (optional) is a type of string
  full_metadata = null
  # metadata - (optional) is a type of string
  metadata = null
  # parent - (required) is a type of string
  parent = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "akas" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_resource" "this" {
  # akas - (optional) is a type of list of string
  akas = var.akas
  # data - (optional) is a type of string
  data = var.data
  # full_data - (optional) is a type of string
  full_data = var.full_data
  # full_metadata - (optional) is a type of string
  full_metadata = var.full_metadata
  # metadata - (optional) is a type of string
  metadata = var.metadata
  # parent - (required) is a type of string
  parent = var.parent
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_resource.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_resource.this.parent_akas
}

output "this" {
  value = turbot_resource.this
}
```

[top](#index)