# oci_core_network_security_group_vnics

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
module "oci_core_network_security_group_vnics" {
  source = "./modules/oci/d/oci_core_network_security_group_vnics"

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
data "oci_core_network_security_group_vnics" "this" {
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
  value       = data.oci_core_network_security_group_vnics.this.id
}

output "network_security_group_vnics" {
  description = "returns a list of object"
  value       = data.oci_core_network_security_group_vnics.this.network_security_group_vnics
}

output "this" {
  value = oci_core_network_security_group_vnics.this
}
```

[top](#index)