# oci_dns_tsig_key

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
module "oci_dns_tsig_key" {
  source = "./modules/oci/d/oci_dns_tsig_key"

  # tsig_key_id - (required) is a type of string
  tsig_key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tsig_key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_tsig_key" "this" {
  tsig_key_id = var.tsig_key_id
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.algorithm
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_tsig_key.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_tsig_key.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.name
}

output "secret" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.secret
  sensitive   = true
}

output "self" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.self
}

output "state" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dns_tsig_key.this.time_updated
}

output "this" {
  value = oci_dns_tsig_key.this
}
```

[top](#index)