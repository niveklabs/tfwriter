# oci_datascience_project

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
module "oci_datascience_project" {
  source = "./modules/oci/r/oci_datascience_project"

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
resource "oci_datascience_project" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags

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
output "created_by" {
  description = "returns a string"
  value       = oci_datascience_project.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datascience_project.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_datascience_project.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_datascience_project.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datascience_project.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datascience_project.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_datascience_project.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datascience_project.this.time_created
}

output "this" {
  value = oci_datascience_project.this
}
```

[top](#index)