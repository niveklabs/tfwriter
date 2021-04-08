# vcd_nsxv_ip_set

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_nsxv_ip_set" {
  source = "./modules/vcd/d/vcd_nsxv_ip_set"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - IP set name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxv_ip_set" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_nsxv_ip_set.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxv_ip_set.this.id
}

output "ip_addresses" {
  description = "returns a set of string"
  value       = data.vcd_nsxv_ip_set.this.ip_addresses
}

output "is_inheritance_allowed" {
  description = "returns a bool"
  value       = data.vcd_nsxv_ip_set.this.is_inheritance_allowed
}

output "this" {
  value = vcd_nsxv_ip_set.this
}
```

[top](#index)