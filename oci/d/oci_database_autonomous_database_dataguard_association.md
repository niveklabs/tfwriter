# oci_database_autonomous_database_dataguard_association

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
module "oci_database_autonomous_database_dataguard_association" {
  source = "./modules/oci/d/oci_database_autonomous_database_dataguard_association"

  # autonomous_database_dataguard_association_id - (required) is a type of string
  autonomous_database_dataguard_association_id = null
  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_database_dataguard_association_id" {
  description = "(required)"
  type        = string
}

variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_database_dataguard_association" "this" {
  # autonomous_database_dataguard_association_id - (required) is a type of string
  autonomous_database_dataguard_association_id = var.autonomous_database_dataguard_association_id
  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = var.autonomous_database_id
}
```

[top](#index)

### Outputs

```terraform
output "apply_lag" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.apply_lag
}

output "apply_rate" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.apply_rate
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.lifecycle_details
}

output "peer_autonomous_database_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.peer_autonomous_database_id
}

output "peer_autonomous_database_life_cycle_state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.peer_autonomous_database_life_cycle_state
}

output "peer_role" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.peer_role
}

output "protection_mode" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.protection_mode
}

output "role" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.role
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.time_created
}

output "time_last_role_changed" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_dataguard_association.this.time_last_role_changed
}

output "this" {
  value = oci_database_autonomous_database_dataguard_association.this
}
```

[top](#index)