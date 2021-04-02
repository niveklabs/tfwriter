# oci_core_vcn_dns_resolver_association

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
module "oci_core_vcn_dns_resolver_association" {
  source = "./modules/oci/d/oci_core_vcn_dns_resolver_association"

  # vcn_id - (required) is a type of string
  vcn_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vcn_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_vcn_dns_resolver_association" "this" {
  vcn_id = var.vcn_id
}
```

[top](#index)

### Outputs

```terraform
output "dns_resolver_id" {
  description = "returns a string"
  value       = data.oci_core_vcn_dns_resolver_association.this.dns_resolver_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_vcn_dns_resolver_association.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_vcn_dns_resolver_association.this.state
}

output "this" {
  value = oci_core_vcn_dns_resolver_association.this
}
```

[top](#index)