# alicloud_config_configuration_recorder

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_config_configuration_recorder" {
  source = "./modules/alicloud/r/alicloud_config_configuration_recorder"

  # enterprise_edition - (optional) is a type of bool
  enterprise_edition = null
  # resource_types - (optional) is a type of set of string
  resource_types = []

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enterprise_edition" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_config_configuration_recorder" "this" {
  enterprise_edition = var.enterprise_edition
  resource_types     = var.resource_types

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_config_configuration_recorder.this.id
}

output "organization_enable_status" {
  description = "returns a string"
  value       = alicloud_config_configuration_recorder.this.organization_enable_status
}

output "organization_master_id" {
  description = "returns a number"
  value       = alicloud_config_configuration_recorder.this.organization_master_id
}

output "resource_types" {
  description = "returns a set of string"
  value       = alicloud_config_configuration_recorder.this.resource_types
}

output "status" {
  description = "returns a string"
  value       = alicloud_config_configuration_recorder.this.status
}

output "this" {
  value = alicloud_config_configuration_recorder.this
}
```

[top](#index)