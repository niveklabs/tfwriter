# oci_osmanagement_managed_instance_group

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
module "oci_osmanagement_managed_instance_group" {
  source = "./modules/oci/r/oci_osmanagement_managed_instance_group"

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
  # os_family - (optional) is a type of string
  os_family = null

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

variable "os_family" {
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
resource "oci_osmanagement_managed_instance_group" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # os_family - (optional) is a type of string
  os_family = var.os_family

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_osmanagement_managed_instance_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_group.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_osmanagement_managed_instance_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_group.this.id
}

output "managed_instance_count" {
  description = "returns a number"
  value       = oci_osmanagement_managed_instance_group.this.managed_instance_count
}

output "managed_instances" {
  description = "returns a list of object"
  value       = oci_osmanagement_managed_instance_group.this.managed_instances
}

output "os_family" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_group.this.os_family
}

output "state" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_group.this.state
}

output "this" {
  value = oci_osmanagement_managed_instance_group.this
}
```

[top](#index)