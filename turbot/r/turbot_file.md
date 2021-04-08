# turbot_file

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
module "turbot_file" {
  source = "./modules/turbot/r/turbot_file"

  # akas - (optional) is a type of list of string
  akas = []
  # content - (optional) is a type of string
  content = null
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

variable "content" {
  description = "(optional)"
  type        = string
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
resource "turbot_file" "this" {
  # akas - (optional) is a type of list of string
  akas = var.akas
  # content - (optional) is a type of string
  content = var.content
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
  value       = turbot_file.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_file.this.parent_akas
}

output "this" {
  value = turbot_file.this
}
```

[top](#index)