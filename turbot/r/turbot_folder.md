# turbot_folder

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
module "turbot_folder" {
  source = "./modules/turbot/r/turbot_folder"

  # akas - (optional) is a type of list of string
  akas = []
  # description - (optional) is a type of string
  description = null
  # parent - (required) is a type of string
  parent = null
  # tags - (optional) is a type of map of string
  tags = {}
  # title - (required) is a type of string
  title = null
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

variable "description" {
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

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_folder" "this" {
  # akas - (optional) is a type of list of string
  akas = var.akas
  # description - (optional) is a type of string
  description = var.description
  # parent - (required) is a type of string
  parent = var.parent
  # tags - (optional) is a type of map of string
  tags = var.tags
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_folder.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_folder.this.parent_akas
}

output "this" {
  value = turbot_folder.this
}
```

[top](#index)