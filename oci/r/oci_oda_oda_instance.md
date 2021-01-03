# oci_oda_oda_instance

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
module "oci_oda_oda_instance" {
  source = "./modules/oci/r/oci_oda_oda_instance"

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
  # shape_name - (required) is a type of string
  shape_name = null
  # state - (optional) is a type of string
  state = null

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

variable "shape_name" {
  description = "(required)"
  type        = string
}

variable "state" {
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
resource "oci_oda_oda_instance" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  shape_name     = var.shape_name
  state          = var.state

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
output "connector_url" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.connector_url
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_oda_oda_instance.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_oda_oda_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.id
}

output "lifecycle_sub_state" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.lifecycle_sub_state
}

output "state" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.state_message
}

output "time_created" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.time_updated
}

output "web_app_url" {
  description = "returns a string"
  value       = oci_oda_oda_instance.this.web_app_url
}

output "this" {
  value = oci_oda_oda_instance.this
}
```

[top](#index)