# oci_cloud_guard_cloud_guard_configuration

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_cloud_guard_cloud_guard_configuration" {
  source = "./modules/oci/r/oci_cloud_guard_cloud_guard_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # reporting_region - (required) is a type of string
  reporting_region = null
  # self_manage_resources - (optional) is a type of bool
  self_manage_resources = null
  # status - (required) is a type of string
  status = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "reporting_region" {
  description = "(required)"
  type        = string
}

variable "self_manage_resources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "status" {
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
resource "oci_cloud_guard_cloud_guard_configuration" "this" {
  compartment_id        = var.compartment_id
  reporting_region      = var.reporting_region
  self_manage_resources = var.self_manage_resources
  status                = var.status

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
output "id" {
  description = "returns a string"
  value       = oci_cloud_guard_cloud_guard_configuration.this.id
}

output "self_manage_resources" {
  description = "returns a bool"
  value       = oci_cloud_guard_cloud_guard_configuration.this.self_manage_resources
}

output "this" {
  value = oci_cloud_guard_cloud_guard_configuration.this
}
```

[top](#index)