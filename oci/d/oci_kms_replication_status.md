# oci_kms_replication_status

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
module "oci_kms_replication_status" {
  source = "./modules/oci/d/oci_kms_replication_status"

  # management_endpoint - (required) is a type of string
  management_endpoint = null
  # replication_id - (required) is a type of string
  replication_id = null
}
```

[top](#index)

### Variables

```terraform
variable "management_endpoint" {
  description = "(required)"
  type        = string
}

variable "replication_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_kms_replication_status" "this" {
  management_endpoint = var.management_endpoint
  replication_id      = var.replication_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_kms_replication_status.this.id
}

output "replica_details" {
  description = "returns a list of object"
  value       = data.oci_kms_replication_status.this.replica_details
}

output "this" {
  value = oci_kms_replication_status.this
}
```

[top](#index)