# oci_limits_quota

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
module "oci_limits_quota" {
  source = "./modules/oci/d/oci_limits_quota"

  # quota_id - (required) is a type of string
  quota_id = null
}
```

[top](#index)

### Variables

```terraform
variable "quota_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_limits_quota" "this" {
  quota_id = var.quota_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_limits_quota.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_limits_quota.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.state
}

output "statements" {
  description = "returns a list of string"
  value       = data.oci_limits_quota.this.statements
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_limits_quota.this.time_created
}

output "this" {
  value = oci_limits_quota.this
}
```

[top](#index)