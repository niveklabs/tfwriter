# oci_waas_waas_policy

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
module "oci_waas_waas_policy" {
  source = "./modules/oci/d/oci_waas_waas_policy"

  # waas_policy_id - (required) is a type of string
  waas_policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "waas_policy_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_waas_policy" "this" {
  # waas_policy_id - (required) is a type of string
  waas_policy_id = var.waas_policy_id
}
```

[top](#index)

### Outputs

```terraform
output "additional_domains" {
  description = "returns a list of string"
  value       = data.oci_waas_waas_policy.this.additional_domains
}

output "cname" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.cname
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_waas_policy.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_waas_policy.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.id
}

output "origin_groups" {
  description = "returns a list of object"
  value       = data.oci_waas_waas_policy.this.origin_groups
}

output "origins" {
  description = "returns a list of object"
  value       = data.oci_waas_waas_policy.this.origins
}

output "policy_config" {
  description = "returns a list of object"
  value       = data.oci_waas_waas_policy.this.policy_config
}

output "state" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_waas_waas_policy.this.time_created
}

output "waf_config" {
  description = "returns a list of object"
  value       = data.oci_waas_waas_policy.this.waf_config
}

output "this" {
  value = oci_waas_waas_policy.this
}
```

[top](#index)