# turbot_local_directory

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
module "turbot_local_directory" {
  source = "./modules/turbot/r/turbot_local_directory"

  # description - (optional) is a type of string
  description = null
  # parent - (required) is a type of string
  parent = null
  # profile_id_template - (required) is a type of string
  profile_id_template = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "parent" {
  description = "(required)"
  type        = string
}

variable "profile_id_template" {
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
resource "turbot_local_directory" "this" {
  # description - (optional) is a type of string
  description = var.description
  # parent - (required) is a type of string
  parent = var.parent
  # profile_id_template - (required) is a type of string
  profile_id_template = var.profile_id_template
  # tags - (optional) is a type of map of string
  tags = var.tags
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "directory_type" {
  description = "returns a string"
  value       = turbot_local_directory.this.directory_type
}

output "id" {
  description = "returns a string"
  value       = turbot_local_directory.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_local_directory.this.parent_akas
}

output "status" {
  description = "returns a string"
  value       = turbot_local_directory.this.status
}

output "this" {
  value = turbot_local_directory.this
}
```

[top](#index)