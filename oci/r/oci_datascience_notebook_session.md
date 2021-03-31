# oci_datascience_notebook_session

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datascience_notebook_session" {
  source = "./modules/oci/r/oci_datascience_notebook_session"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # project_id - (required) is a type of string
  project_id = null
  # state - (optional) is a type of string
  state = null

  notebook_session_configuration_details = [{
    block_storage_size_in_gbs = null
    shape                     = null
    subnet_id                 = null
  }]

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

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notebook_session_configuration_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      block_storage_size_in_gbs = number
      shape                     = string
      subnet_id                 = string
    }
  ))
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
resource "oci_datascience_notebook_session" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  project_id     = var.project_id
  state          = var.state

  dynamic "notebook_session_configuration_details" {
    for_each = var.notebook_session_configuration_details
    content {
      block_storage_size_in_gbs = notebook_session_configuration_details.value["block_storage_size_in_gbs"]
      shape                     = notebook_session_configuration_details.value["shape"]
      subnet_id                 = notebook_session_configuration_details.value["subnet_id"]
    }
  }

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
  value       = oci_datascience_notebook_session.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datascience_notebook_session.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datascience_notebook_session.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.lifecycle_details
}

output "notebook_session_url" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.notebook_session_url
}

output "state" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datascience_notebook_session.this.time_created
}

output "this" {
  value = oci_datascience_notebook_session.this
}
```

[top](#index)