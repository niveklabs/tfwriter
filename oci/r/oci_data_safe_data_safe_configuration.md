# oci_data_safe_data_safe_configuration

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_data_safe_data_safe_configuration" {
  source = "./modules/oci/r/oci_data_safe_data_safe_configuration"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # is_enabled - (required) is a type of bool
  is_enabled = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_enabled" {
  description = "(required)"
  type        = bool
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
resource "oci_data_safe_data_safe_configuration" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # is_enabled - (required) is a type of bool
  is_enabled = var.is_enabled

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_configuration.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_configuration.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_configuration.this.state
}

output "time_enabled" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_configuration.this.time_enabled
}

output "url" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_configuration.this.url
}

output "this" {
  value = oci_data_safe_data_safe_configuration.this
}
```

[top](#index)