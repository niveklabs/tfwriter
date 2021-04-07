# oci_datascience_model

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
module "oci_datascience_model" {
  source = "./modules/oci/r/oci_datascience_model"

  # artifact_content_disposition - (optional) is a type of string
  artifact_content_disposition = null
  # artifact_content_length - (required) is a type of string
  artifact_content_length = null
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
  # model_artifact - (required) is a type of string
  model_artifact = null
  # project_id - (required) is a type of string
  project_id = null
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
variable "artifact_content_disposition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "artifact_content_length" {
  description = "(required)"
  type        = string
}

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

variable "model_artifact" {
  description = "(required)"
  type        = string
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
resource "oci_datascience_model" "this" {
  # artifact_content_disposition - (optional) is a type of string
  artifact_content_disposition = var.artifact_content_disposition
  # artifact_content_length - (required) is a type of string
  artifact_content_length = var.artifact_content_length
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
  # model_artifact - (required) is a type of string
  model_artifact = var.model_artifact
  # project_id - (required) is a type of string
  project_id = var.project_id
  # state - (optional) is a type of string
  state = var.state

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
output "artifact_content_disposition" {
  description = "returns a string"
  value       = oci_datascience_model.this.artifact_content_disposition
}

output "artifact_content_md5" {
  description = "returns a string"
  value       = oci_datascience_model.this.artifact_content_md5
}

output "artifact_last_modified" {
  description = "returns a string"
  value       = oci_datascience_model.this.artifact_last_modified
}

output "created_by" {
  description = "returns a string"
  value       = oci_datascience_model.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datascience_model.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_datascience_model.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_datascience_model.this.display_name
}

output "empty_model" {
  description = "returns a bool"
  value       = oci_datascience_model.this.empty_model
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datascience_model.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datascience_model.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_datascience_model.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datascience_model.this.time_created
}

output "this" {
  value = oci_datascience_model.this
}
```

[top](#index)