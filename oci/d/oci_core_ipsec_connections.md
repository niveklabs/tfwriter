# oci_core_ipsec_connections

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
module "oci_core_ipsec_connections" {
  source = "./modules/oci/d/oci_core_ipsec_connections"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpe_id - (optional) is a type of string
  cpe_id = null
  # drg_id - (optional) is a type of string
  drg_id = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "cpe_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drg_id" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_core_ipsec_connections" "this" {
  compartment_id = var.compartment_id
  cpe_id         = var.cpe_id
  drg_id         = var.drg_id

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
output "connections" {
  description = "returns a list of object"
  value       = data.oci_core_ipsec_connections.this.connections
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connections.this.id
}

output "this" {
  value = oci_core_ipsec_connections.this
}
```

[top](#index)