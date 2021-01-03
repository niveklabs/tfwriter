# oci_database_autonomous_database_instance_wallet_management

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
module "oci_database_autonomous_database_instance_wallet_management" {
  source = "./modules/oci/d/oci_database_autonomous_database_instance_wallet_management"

  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_database_instance_wallet_management" "this" {
  autonomous_database_id = var.autonomous_database_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_instance_wallet_management.this.id
}

output "should_rotate" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database_instance_wallet_management.this.should_rotate
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_instance_wallet_management.this.state
}

output "time_rotated" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_instance_wallet_management.this.time_rotated
}

output "this" {
  value = oci_database_autonomous_database_instance_wallet_management.this
}
```

[top](#index)