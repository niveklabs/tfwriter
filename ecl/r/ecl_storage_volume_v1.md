# ecl_storage_volume_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_storage_volume_v1" {
  source = "./modules/ecl/r/ecl_storage_volume_v1"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # error_message - (optional) is a type of string
  error_message = null
  # initiator_iqns - (optional) is a type of set of string
  initiator_iqns = []
  # iops_per_gb - (optional) is a type of string
  iops_per_gb = null
  # name - (required) is a type of string
  name = null
  # size - (required) is a type of number
  size = null
  # throughput - (optional) is a type of string
  throughput = null
  # virtual_storage_id - (required) is a type of string
  virtual_storage_id = null

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
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "error_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "initiator_iqns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "iops_per_gb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "throughput" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_storage_id" {
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
resource "ecl_storage_volume_v1" "this" {
  availability_zone  = var.availability_zone
  description        = var.description
  error_message      = var.error_message
  initiator_iqns     = var.initiator_iqns
  iops_per_gb        = var.iops_per_gb
  name               = var.name
  size               = var.size
  throughput         = var.throughput
  virtual_storage_id = var.virtual_storage_id

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
output "availability_zone" {
  description = "returns a string"
  value       = ecl_storage_volume_v1.this.availability_zone
}

output "error_message" {
  description = "returns a string"
  value       = ecl_storage_volume_v1.this.error_message
}

output "id" {
  description = "returns a string"
  value       = ecl_storage_volume_v1.this.id
}

output "this" {
  value = ecl_storage_volume_v1.this
}
```

[top](#index)