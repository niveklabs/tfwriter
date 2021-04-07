# alicloud_fc_alias

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
module "alicloud_fc_alias" {
  source = "./modules/alicloud/r/alicloud_fc_alias"

  # alias_name - (required) is a type of string
  alias_name = null
  # description - (optional) is a type of string
  description = null
  # service_name - (required) is a type of string
  service_name = null
  # service_version - (required) is a type of string
  service_version = null

  routing_config = [{
    additional_version_weights = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alias_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "service_version" {
  description = "(required)"
  type        = string
}

variable "routing_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      additional_version_weights = map(number)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fc_alias" "this" {
  # alias_name - (required) is a type of string
  alias_name = var.alias_name
  # description - (optional) is a type of string
  description = var.description
  # service_name - (required) is a type of string
  service_name = var.service_name
  # service_version - (required) is a type of string
  service_version = var.service_version

  dynamic "routing_config" {
    for_each = var.routing_config
    content {
      # additional_version_weights - (optional) is a type of map of number
      additional_version_weights = routing_config.value["additional_version_weights"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_fc_alias.this.id
}

output "this" {
  value = alicloud_fc_alias.this
}
```

[top](#index)