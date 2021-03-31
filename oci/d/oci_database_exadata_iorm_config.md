# oci_database_exadata_iorm_config

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
module "oci_database_exadata_iorm_config" {
  source = "./modules/oci/d/oci_database_exadata_iorm_config"

  # db_system_id - (required) is a type of string
  db_system_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_system_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_exadata_iorm_config" "this" {
  db_system_id = var.db_system_id
}
```

[top](#index)

### Outputs

```terraform
output "db_plans" {
  description = "returns a list of object"
  value       = data.oci_database_exadata_iorm_config.this.db_plans
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_exadata_iorm_config.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_exadata_iorm_config.this.lifecycle_details
}

output "objective" {
  description = "returns a string"
  value       = data.oci_database_exadata_iorm_config.this.objective
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_exadata_iorm_config.this.state
}

output "this" {
  value = oci_database_exadata_iorm_config.this
}
```

[top](#index)