# oci_email_suppression

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
module "oci_email_suppression" {
  source = "./modules/oci/d/oci_email_suppression"

  # suppression_id - (required) is a type of string
  suppression_id = null
}
```

[top](#index)

### Variables

```terraform
variable "suppression_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_email_suppression" "this" {
  suppression_id = var.suppression_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_email_suppression.this.compartment_id
}

output "email_address" {
  description = "returns a string"
  value       = data.oci_email_suppression.this.email_address
}

output "id" {
  description = "returns a string"
  value       = data.oci_email_suppression.this.id
}

output "reason" {
  description = "returns a string"
  value       = data.oci_email_suppression.this.reason
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_email_suppression.this.time_created
}

output "this" {
  value = oci_email_suppression.this
}
```

[top](#index)