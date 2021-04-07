# oci_mysql_mysql_configuration

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
module "oci_mysql_mysql_configuration" {
  source = "./modules/oci/d/oci_mysql_mysql_configuration"

  # configuration_id - (required) is a type of string
  configuration_id = null
}
```

[top](#index)

### Variables

```terraform
variable "configuration_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_mysql_mysql_configuration" "this" {
  configuration_id = var.configuration_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_mysql_configuration.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_mysql_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.id
}

output "parent_configuration_id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.parent_configuration_id
}

output "shape_name" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.shape_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.time_updated
}

output "type" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configuration.this.type
}

output "variables" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_configuration.this.variables
}

output "this" {
  value = oci_mysql_mysql_configuration.this
}
```

[top](#index)