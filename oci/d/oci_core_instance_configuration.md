# oci_core_instance_configuration

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
module "oci_core_instance_configuration" {
  source = "./modules/oci/d/oci_core_instance_configuration"

  # instance_configuration_id - (required) is a type of string
  instance_configuration_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_configuration_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_instance_configuration" "this" {
  instance_configuration_id = var.instance_configuration_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.compartment_id
}

output "deferred_fields" {
  description = "returns a list of string"
  value       = data.oci_core_instance_configuration.this.deferred_fields
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_instance_configuration.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_instance_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.id
}

output "instance_details" {
  description = "returns a list of object"
  value       = data.oci_core_instance_configuration.this.instance_details
}

output "instance_id" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.instance_id
}

output "source" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.source
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_instance_configuration.this.time_created
}

output "this" {
  value = oci_core_instance_configuration.this
}
```

[top](#index)