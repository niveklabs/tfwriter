# oci_streaming_stream_pool

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_streaming_stream_pool" {
  source = "./modules/oci/d/oci_streaming_stream_pool"

  # stream_pool_id - (required) is a type of string
  stream_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "stream_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_streaming_stream_pool" "this" {
  stream_pool_id = var.stream_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.compartment_id
}

output "custom_encryption_key" {
  description = "returns a list of object"
  value       = data.oci_streaming_stream_pool.this.custom_encryption_key
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_stream_pool.this.defined_tags
}

output "endpoint_fqdn" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.endpoint_fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_stream_pool.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.id
}

output "is_private" {
  description = "returns a bool"
  value       = data.oci_streaming_stream_pool.this.is_private
}

output "kafka_settings" {
  description = "returns a list of object"
  value       = data.oci_streaming_stream_pool.this.kafka_settings
}

output "lifecycle_state_details" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.lifecycle_state_details
}

output "name" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.name
}

output "private_endpoint_settings" {
  description = "returns a list of object"
  value       = data.oci_streaming_stream_pool.this.private_endpoint_settings
}

output "state" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_streaming_stream_pool.this.time_created
}

output "this" {
  value = oci_streaming_stream_pool.this
}
```

[top](#index)