# oci_data_safe_on_prem_connector

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
module "oci_data_safe_on_prem_connector" {
  source = "./modules/oci/r/oci_data_safe_on_prem_connector"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
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
resource "oci_data_safe_on_prem_connector" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags

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
output "available_version" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.available_version
}

output "created_version" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.created_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_data_safe_on_prem_connector.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_data_safe_on_prem_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_data_safe_on_prem_connector.this.time_created
}

output "this" {
  value = oci_data_safe_on_prem_connector.this
}
```

[top](#index)