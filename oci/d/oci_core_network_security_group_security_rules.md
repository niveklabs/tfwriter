# oci_core_network_security_group_security_rules

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
module "oci_core_network_security_group_security_rules" {
  source = "./modules/oci/d/oci_core_network_security_group_security_rules"

  # direction - (optional) is a type of string
  direction = null
  # network_security_group_id - (required) is a type of string
  network_security_group_id = null

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
variable "direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_security_group_id" {
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
data "oci_core_network_security_group_security_rules" "this" {
  direction                 = var.direction
  network_security_group_id = var.network_security_group_id

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
output "id" {
  description = "returns a string"
  value       = data.oci_core_network_security_group_security_rules.this.id
}

output "security_rules" {
  description = "returns a list of object"
  value       = data.oci_core_network_security_group_security_rules.this.security_rules
}

output "this" {
  value = oci_core_network_security_group_security_rules.this
}
```

[top](#index)