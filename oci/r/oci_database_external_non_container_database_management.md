# oci_database_external_non_container_database_management

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
module "oci_database_external_non_container_database_management" {
  source = "./modules/oci/r/oci_database_external_non_container_database_management"

  # enable_management - (required) is a type of bool
  enable_management = null
  # external_database_connector_id - (required) is a type of string
  external_database_connector_id = null
  # external_non_container_database_id - (required) is a type of string
  external_non_container_database_id = null
  # license_model - (optional) is a type of string
  license_model = null

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
variable "enable_management" {
  description = "(required)"
  type        = bool
}

variable "external_database_connector_id" {
  description = "(required)"
  type        = string
}

variable "external_non_container_database_id" {
  description = "(required)"
  type        = string
}

variable "license_model" {
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
resource "oci_database_external_non_container_database_management" "this" {
  # enable_management - (required) is a type of bool
  enable_management = var.enable_management
  # external_database_connector_id - (required) is a type of string
  external_database_connector_id = var.external_database_connector_id
  # external_non_container_database_id - (required) is a type of string
  external_non_container_database_id = var.external_non_container_database_id
  # license_model - (optional) is a type of string
  license_model = var.license_model

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
output "id" {
  description = "returns a string"
  value       = oci_database_external_non_container_database_management.this.id
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_external_non_container_database_management.this.license_model
}

output "this" {
  value = oci_database_external_non_container_database_management.this
}
```

[top](#index)