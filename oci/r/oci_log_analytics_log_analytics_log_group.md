# oci_log_analytics_log_analytics_log_group

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
module "oci_log_analytics_log_analytics_log_group" {
  source = "./modules/oci/r/oci_log_analytics_log_analytics_log_group"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # namespace - (required) is a type of string
  namespace = null

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
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "namespace" {
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
resource "oci_log_analytics_log_analytics_log_group" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  namespace      = var.namespace

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_log_analytics_log_analytics_log_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_log_group.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_log_analytics_log_analytics_log_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_log_group.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_log_group.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_log_group.this.time_updated
}

output "this" {
  value = oci_log_analytics_log_analytics_log_group.this
}
```

[top](#index)