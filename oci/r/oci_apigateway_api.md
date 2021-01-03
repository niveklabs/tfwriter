# oci_apigateway_api

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
module "oci_apigateway_api" {
  source = "./modules/oci/r/oci_apigateway_api"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # content - (optional) is a type of string
  content = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
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

variable "content" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_apigateway_api" "this" {
  compartment_id = var.compartment_id
  content        = var.content
  defined_tags   = var.defined_tags
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
output "content" {
  description = "returns a string"
  value       = oci_apigateway_api.this.content
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_api.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_apigateway_api.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_api.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_apigateway_api.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_apigateway_api.this.lifecycle_details
}

output "specification_type" {
  description = "returns a string"
  value       = oci_apigateway_api.this.specification_type
}

output "state" {
  description = "returns a string"
  value       = oci_apigateway_api.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_apigateway_api.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_apigateway_api.this.time_updated
}

output "validation_results" {
  description = "returns a list of object"
  value       = oci_apigateway_api.this.validation_results
}

output "this" {
  value = oci_apigateway_api.this
}
```

[top](#index)