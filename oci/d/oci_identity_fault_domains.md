# oci_identity_fault_domains

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
module "oci_identity_fault_domains" {
  source = "./modules/oci/d/oci_identity_fault_domains"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_fault_domains" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fault_domains" {
  description = "returns a list of object"
  value       = data.oci_identity_fault_domains.this.fault_domains
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_fault_domains.this.id
}

output "this" {
  value = oci_identity_fault_domains.this
}
```

[top](#index)