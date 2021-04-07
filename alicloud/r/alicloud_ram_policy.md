# alicloud_ram_policy

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_policy" {
  source = "./modules/alicloud/r/alicloud_ram_policy"

  # description - (optional) is a type of string
  description = null
  # document - (optional) is a type of string
  document = null
  # force - (optional) is a type of bool
  force = null
  # name - (optional) is a type of string
  name = null
  # policy_document - (optional) is a type of string
  policy_document = null
  # policy_name - (optional) is a type of string
  policy_name = null
  # rotate_strategy - (optional) is a type of string
  rotate_strategy = null
  # version - (optional) is a type of string
  version = null

  statement = [{
    action   = []
    effect   = null
    resource = []
  }]

  timeouts = [{
    delete = null
  }]
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

variable "document" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_document" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotate_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action   = list(string)
      effect   = string
      resource = list(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # document - (optional) is a type of string
  document = var.document
  # force - (optional) is a type of bool
  force = var.force
  # name - (optional) is a type of string
  name = var.name
  # policy_document - (optional) is a type of string
  policy_document = var.policy_document
  # policy_name - (optional) is a type of string
  policy_name = var.policy_name
  # rotate_strategy - (optional) is a type of string
  rotate_strategy = var.rotate_strategy
  # version - (optional) is a type of string
  version = var.version

  dynamic "statement" {
    for_each = var.statement
    content {
      # action - (required) is a type of list of string
      action = statement.value["action"]
      # effect - (required) is a type of string
      effect = statement.value["effect"]
      # resource - (required) is a type of list of string
      resource = statement.value["resource"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attachment_count" {
  description = "returns a number"
  value       = alicloud_ram_policy.this.attachment_count
}

output "default_version" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.default_version
}

output "document" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.document
}

output "id" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.name
}

output "policy_document" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.policy_document
}

output "policy_name" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.policy_name
}

output "type" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.type
}

output "version_id" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.version_id
}

output "this" {
  value = alicloud_ram_policy.this
}
```

[top](#index)