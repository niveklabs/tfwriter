# oci_streaming_stream

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "oci_streaming_stream" {
  source = "./modules/oci/d/oci_streaming_stream"

  # stream_id - (required) is a type of string
  stream_id = null
}
```

[top](#index)

### Variables

```terraform
variable "stream_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_streaming_stream" "this" {
  stream_id = var.stream_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_stream.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_stream.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.id
}

output "lifecycle_state_details" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.lifecycle_state_details
}

output "messages_endpoint" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.messages_endpoint
}

output "name" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.name
}

output "partitions" {
  description = "returns a number"
  value       = data.oci_streaming_stream.this.partitions
}

output "retention_in_hours" {
  description = "returns a number"
  value       = data.oci_streaming_stream.this.retention_in_hours
}

output "state" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.state
}

output "stream_pool_id" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.stream_pool_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_streaming_stream.this.time_created
}

output "this" {
  value = oci_streaming_stream.this
}
```

[top](#index)