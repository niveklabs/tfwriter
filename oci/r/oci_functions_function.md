# oci_functions_function

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
module "oci_functions_function" {
  source = "./modules/oci/r/oci_functions_function"

  # application_id - (required) is a type of string
  application_id = null
  # config - (optional) is a type of map of string
  config = {}
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # image - (required) is a type of string
  image = null
  # image_digest - (optional) is a type of string
  image_digest = null
  # memory_in_mbs - (required) is a type of string
  memory_in_mbs = null
  # timeout_in_seconds - (optional) is a type of number
  timeout_in_seconds = null

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
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "image" {
  description = "(required)"
  type        = string
}

variable "image_digest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_in_mbs" {
  description = "(required)"
  type        = string
}

variable "timeout_in_seconds" {
  description = "(optional)"
  type        = number
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
resource "oci_functions_function" "this" {
  application_id     = var.application_id
  config             = var.config
  defined_tags       = var.defined_tags
  display_name       = var.display_name
  freeform_tags      = var.freeform_tags
  image              = var.image
  image_digest       = var.image_digest
  memory_in_mbs      = var.memory_in_mbs
  timeout_in_seconds = var.timeout_in_seconds

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_functions_function.this.compartment_id
}

output "config" {
  description = "returns a map of string"
  value       = oci_functions_function.this.config
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_functions_function.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_functions_function.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_functions_function.this.id
}

output "image_digest" {
  description = "returns a string"
  value       = oci_functions_function.this.image_digest
}

output "invoke_endpoint" {
  description = "returns a string"
  value       = oci_functions_function.this.invoke_endpoint
}

output "state" {
  description = "returns a string"
  value       = oci_functions_function.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_functions_function.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_functions_function.this.time_updated
}

output "timeout_in_seconds" {
  description = "returns a number"
  value       = oci_functions_function.this.timeout_in_seconds
}

output "this" {
  value = oci_functions_function.this
}
```

[top](#index)