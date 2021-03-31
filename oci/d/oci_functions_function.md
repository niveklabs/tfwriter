# oci_functions_function

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
module "oci_functions_function" {
  source = "./modules/oci/d/oci_functions_function"

  # function_id - (required) is a type of string
  function_id = null
}
```

[top](#index)

### Variables

```terraform
variable "function_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_functions_function" "this" {
  function_id = var.function_id
}
```

[top](#index)

### Outputs

```terraform
output "application_id" {
  description = "returns a string"
  value       = data.oci_functions_function.this.application_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_functions_function.this.compartment_id
}

output "config" {
  description = "returns a map of string"
  value       = data.oci_functions_function.this.config
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_functions_function.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_functions_function.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_functions_function.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_functions_function.this.id
}

output "image" {
  description = "returns a string"
  value       = data.oci_functions_function.this.image
}

output "image_digest" {
  description = "returns a string"
  value       = data.oci_functions_function.this.image_digest
}

output "invoke_endpoint" {
  description = "returns a string"
  value       = data.oci_functions_function.this.invoke_endpoint
}

output "memory_in_mbs" {
  description = "returns a string"
  value       = data.oci_functions_function.this.memory_in_mbs
}

output "state" {
  description = "returns a string"
  value       = data.oci_functions_function.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_functions_function.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_functions_function.this.time_updated
}

output "timeout_in_seconds" {
  description = "returns a number"
  value       = data.oci_functions_function.this.timeout_in_seconds
}

output "this" {
  value = oci_functions_function.this
}
```

[top](#index)