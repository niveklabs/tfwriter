# oci_core_ipsec_config

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
module "oci_core_ipsec_config" {
  source = "./modules/oci/d/oci_core_ipsec_config"

  # ipsec_id - (required) is a type of string
  ipsec_id = null

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
variable "ipsec_id" {
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
data "oci_core_ipsec_config" "this" {
  ipsec_id = var.ipsec_id

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
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_ipsec_config.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_ipsec_config.this.id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_ipsec_config.this.time_created
}

output "tunnels" {
  description = "returns a list of object"
  value       = data.oci_core_ipsec_config.this.tunnels
}

output "this" {
  value = oci_core_ipsec_config.this
}
```

[top](#index)