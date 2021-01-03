# oci_core_instance_pool

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
module "oci_core_instance_pool" {
  source = "./modules/oci/d/oci_core_instance_pool"

  # instance_pool_id - (required) is a type of string
  instance_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_instance_pool" "this" {
  instance_pool_id = var.instance_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "actual_size" {
  description = "returns a number"
  value       = data.oci_core_instance_pool.this.actual_size
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_instance_pool.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_instance_pool.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.id
}

output "instance_configuration_id" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.instance_configuration_id
}

output "load_balancers" {
  description = "returns a list of object"
  value       = data.oci_core_instance_pool.this.load_balancers
}

output "placement_configurations" {
  description = "returns a list of object"
  value       = data.oci_core_instance_pool.this.placement_configurations
}

output "size" {
  description = "returns a number"
  value       = data.oci_core_instance_pool.this.size
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_instance_pool.this.time_created
}

output "this" {
  value = oci_core_instance_pool.this
}
```

[top](#index)