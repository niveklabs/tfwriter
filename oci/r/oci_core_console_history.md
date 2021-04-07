# oci_core_console_history

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
module "oci_core_console_history" {
  source = "./modules/oci/r/oci_core_console_history"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # instance_id - (required) is a type of string
  instance_id = null

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
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "instance_id" {
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
resource "oci_core_console_history" "this" {
  defined_tags  = var.defined_tags
  display_name  = var.display_name
  freeform_tags = var.freeform_tags
  instance_id   = var.instance_id

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
output "availability_domain" {
  description = "returns a string"
  value       = oci_core_console_history.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_console_history.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_console_history.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_console_history.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_console_history.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_console_history.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_console_history.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_console_history.this.time_created
}

output "this" {
  value = oci_core_console_history.this
}
```

[top](#index)