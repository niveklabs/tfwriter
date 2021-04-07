# oci_bds_auto_scaling_configuration

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
module "oci_bds_auto_scaling_configuration" {
  source = "./modules/oci/d/oci_bds_auto_scaling_configuration"

  # auto_scaling_configuration_id - (required) is a type of string
  auto_scaling_configuration_id = null
  # bds_instance_id - (required) is a type of string
  bds_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_scaling_configuration_id" {
  description = "(required)"
  type        = string
}

variable "bds_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_bds_auto_scaling_configuration" "this" {
  auto_scaling_configuration_id = var.auto_scaling_configuration_id
  bds_instance_id               = var.bds_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "cluster_admin_password" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.cluster_admin_password
  sensitive   = true
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_bds_auto_scaling_configuration.this.is_enabled
}

output "node_type" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.node_type
}

output "policy" {
  description = "returns a list of object"
  value       = data.oci_bds_auto_scaling_configuration.this.policy
}

output "state" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_bds_auto_scaling_configuration.this.time_updated
}

output "this" {
  value = oci_bds_auto_scaling_configuration.this
}
```

[top](#index)