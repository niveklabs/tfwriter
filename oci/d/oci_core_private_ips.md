# oci_core_private_ips

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
module "oci_core_private_ips" {
  source = "./modules/oci/d/oci_core_private_ips"

  # ip_address - (optional) is a type of string
  ip_address = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # vlan_id - (optional) is a type of string
  vlan_id = null
  # vnic_id - (optional) is a type of string
  vnic_id = null

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
variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnic_id" {
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
data "oci_core_private_ips" "this" {
  ip_address = var.ip_address
  subnet_id  = var.subnet_id
  vlan_id    = var.vlan_id
  vnic_id    = var.vnic_id

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
  value       = data.oci_core_private_ips.this.id
}

output "private_ips" {
  description = "returns a list of object"
  value       = data.oci_core_private_ips.this.private_ips
}

output "this" {
  value = oci_core_private_ips.this
}
```

[top](#index)