# oci_database_autonomous_exadata_infrastructure_ocpu

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_exadata_infrastructure_ocpu" {
  source = "./modules/oci/d/oci_database_autonomous_exadata_infrastructure_ocpu"

  # autonomous_exadata_infrastructure_id - (required) is a type of string
  autonomous_exadata_infrastructure_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_exadata_infrastructure_ocpu" "this" {
  autonomous_exadata_infrastructure_id = var.autonomous_exadata_infrastructure_id
}
```

[top](#index)

### Outputs

```terraform
output "by_workload_type" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_exadata_infrastructure_ocpu.this.by_workload_type
}

output "consumed_cpu" {
  description = "returns a number"
  value       = data.oci_database_autonomous_exadata_infrastructure_ocpu.this.consumed_cpu
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure_ocpu.this.id
}

output "total_cpu" {
  description = "returns a number"
  value       = data.oci_database_autonomous_exadata_infrastructure_ocpu.this.total_cpu
}

output "this" {
  value = oci_database_autonomous_exadata_infrastructure_ocpu.this
}
```

[top](#index)