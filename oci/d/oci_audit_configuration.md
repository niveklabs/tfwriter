# oci_audit_configuration

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
module "oci_audit_configuration" {
  source = "./modules/oci/d/oci_audit_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_audit_configuration" "this" {
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_audit_configuration.this.id
}

output "retention_period_days" {
  description = "returns a number"
  value       = data.oci_audit_configuration.this.retention_period_days
}

output "this" {
  value = oci_audit_configuration.this
}
```

[top](#index)