# turbot_smart_folder

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
module "turbot_smart_folder" {
  source = "./modules/turbot/r/turbot_smart_folder"

  # description - (optional) is a type of string
  description = null
  # filter - (optional) is a type of string
  filter = null
  # parent - (required) is a type of string
  parent = null
  # title - (required) is a type of string
  title = null
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

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_smart_folder" "this" {
  # description - (optional) is a type of string
  description = var.description
  # filter - (optional) is a type of string
  filter = var.filter
  # parent - (required) is a type of string
  parent = var.parent
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_smart_folder.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_smart_folder.this.parent_akas
}

output "this" {
  value = turbot_smart_folder.this
}
```

[top](#index)