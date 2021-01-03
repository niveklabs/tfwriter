# oci_osmanagement_managed_instance_group

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
module "oci_osmanagement_managed_instance_group" {
  source = "./modules/oci/d/oci_osmanagement_managed_instance_group"

  # managed_instance_group_id - (required) is a type of string
  managed_instance_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_instance_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_osmanagement_managed_instance_group" "this" {
  managed_instance_group_id = var.managed_instance_group_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_osmanagement_managed_instance_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_osmanagement_managed_instance_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.id
}

output "managed_instance_count" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance_group.this.managed_instance_count
}

output "managed_instances" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_managed_instance_group.this.managed_instances
}

output "os_family" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.os_family
}

output "state" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance_group.this.state
}

output "this" {
  value = oci_osmanagement_managed_instance_group.this
}
```

[top](#index)