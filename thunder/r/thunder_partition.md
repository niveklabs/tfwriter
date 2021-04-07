# thunder_partition

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_partition" {
  source = "./modules/thunder/r/thunder_partition"

  # application_type - (optional) is a type of string
  application_type = null
  # id2 - (optional) is a type of number
  id2 = null
  # partition_name - (optional) is a type of string
  partition_name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  shared_vlan = [{
    mgmt_floating_ip_address = null
    uuid                     = null
    vlan                     = null
    vrid                     = null
  }]

  template = [{
    resource_accounting = null
    uuid                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "id2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "partition_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_vlan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      mgmt_floating_ip_address = string
      uuid                     = string
      vlan                     = number
      vrid                     = number
    }
  ))
  default = []
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      resource_accounting = string
      uuid                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_partition" "this" {
  # application_type - (optional) is a type of string
  application_type = var.application_type
  # id2 - (optional) is a type of number
  id2 = var.id2
  # partition_name - (optional) is a type of string
  partition_name = var.partition_name
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "shared_vlan" {
    for_each = var.shared_vlan
    content {
      # mgmt_floating_ip_address - (optional) is a type of string
      mgmt_floating_ip_address = shared_vlan.value["mgmt_floating_ip_address"]
      # uuid - (optional) is a type of string
      uuid = shared_vlan.value["uuid"]
      # vlan - (optional) is a type of number
      vlan = shared_vlan.value["vlan"]
      # vrid - (optional) is a type of number
      vrid = shared_vlan.value["vrid"]
    }
  }

  dynamic "template" {
    for_each = var.template
    content {
      # resource_accounting - (optional) is a type of string
      resource_accounting = template.value["resource_accounting"]
      # uuid - (optional) is a type of string
      uuid = template.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_partition.this.id
}

output "this" {
  value = thunder_partition.this
}
```

[top](#index)