# oci_streaming_connect_harness

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_streaming_connect_harness" {
  source = "./modules/oci/d/oci_streaming_connect_harness"

  # connect_harness_id - (required) is a type of string
  connect_harness_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connect_harness_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_streaming_connect_harness" "this" {
  connect_harness_id = var.connect_harness_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_connect_harness.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_streaming_connect_harness.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.id
}

output "lifecycle_state_details" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.lifecycle_state_details
}

output "name" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_streaming_connect_harness.this.time_created
}

output "this" {
  value = oci_streaming_connect_harness.this
}
```

[top](#index)