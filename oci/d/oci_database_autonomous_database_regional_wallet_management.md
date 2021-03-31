# oci_database_autonomous_database_regional_wallet_management

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
module "oci_database_autonomous_database_regional_wallet_management" {
  source = "./modules/oci/d/oci_database_autonomous_database_regional_wallet_management"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_database_regional_wallet_management" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_regional_wallet_management.this.id
}

output "should_rotate" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database_regional_wallet_management.this.should_rotate
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_regional_wallet_management.this.state
}

output "time_rotated" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_regional_wallet_management.this.time_rotated
}

output "this" {
  value = oci_database_autonomous_database_regional_wallet_management.this
}
```

[top](#index)