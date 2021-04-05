# alicloud_fnf_flow

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
module "alicloud_fnf_flow" {
  source = "./modules/alicloud/r/alicloud_fnf_flow"

  # definition - (required) is a type of string
  definition = null
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # type - (required) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "definition" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fnf_flow" "this" {
  definition  = var.definition
  description = var.description
  name        = var.name
  role_arn    = var.role_arn
  type        = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "flow_id" {
  description = "returns a string"
  value       = alicloud_fnf_flow.this.flow_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_fnf_flow.this.id
}

output "last_modified_time" {
  description = "returns a string"
  value       = alicloud_fnf_flow.this.last_modified_time
}

output "this" {
  value = alicloud_fnf_flow.this
}
```

[top](#index)