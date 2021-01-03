# oci_management_agent_management_agent_install_key

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_agent_management_agent_install_key" {
  source = "./modules/oci/r/oci_management_agent_management_agent_install_key"

  # allowed_key_install_count - (optional) is a type of number
  allowed_key_install_count = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (required) is a type of string
  display_name = null
  # time_expires - (optional) is a type of string
  time_expires = null

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
variable "allowed_key_install_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "time_expires" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_management_agent_management_agent_install_key" "this" {
  allowed_key_install_count = var.allowed_key_install_count
  compartment_id            = var.compartment_id
  display_name              = var.display_name
  time_expires              = var.time_expires

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
output "allowed_key_install_count" {
  description = "returns a number"
  value       = oci_management_agent_management_agent_install_key.this.allowed_key_install_count
}

output "created_by_principal_id" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.created_by_principal_id
}

output "current_key_install_count" {
  description = "returns a number"
  value       = oci_management_agent_management_agent_install_key.this.current_key_install_count
}

output "id" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.id
}

output "key" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.key
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.time_created
}

output "time_expires" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.time_expires
}

output "time_updated" {
  description = "returns a string"
  value       = oci_management_agent_management_agent_install_key.this.time_updated
}

output "this" {
  value = oci_management_agent_management_agent_install_key.this
}
```

[top](#index)