# oci_streaming_stream

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
module "oci_streaming_stream" {
  source = "./modules/oci/r/oci_streaming_stream"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null
  # partitions - (required) is a type of number
  partitions = null
  # retention_in_hours - (optional) is a type of number
  retention_in_hours = null
  # stream_pool_id - (optional) is a type of string
  stream_pool_id = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "partitions" {
  description = "(required)"
  type        = number
}

variable "retention_in_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stream_pool_id" {
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
resource "oci_streaming_stream" "this" {
  compartment_id     = var.compartment_id
  defined_tags       = var.defined_tags
  freeform_tags      = var.freeform_tags
  name               = var.name
  partitions         = var.partitions
  retention_in_hours = var.retention_in_hours
  stream_pool_id     = var.stream_pool_id

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
  value       = oci_streaming_stream.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_streaming_stream.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_streaming_stream.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_streaming_stream.this.id
}

output "lifecycle_state_details" {
  description = "returns a string"
  value       = oci_streaming_stream.this.lifecycle_state_details
}

output "messages_endpoint" {
  description = "returns a string"
  value       = oci_streaming_stream.this.messages_endpoint
}

output "retention_in_hours" {
  description = "returns a number"
  value       = oci_streaming_stream.this.retention_in_hours
}

output "state" {
  description = "returns a string"
  value       = oci_streaming_stream.this.state
}

output "stream_pool_id" {
  description = "returns a string"
  value       = oci_streaming_stream.this.stream_pool_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_streaming_stream.this.time_created
}

output "this" {
  value = oci_streaming_stream.this
}
```

[top](#index)