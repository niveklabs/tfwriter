# vcd_nsxv_ip_set

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vcd/r/vcd_nsxv_ip_set"

  # description - (optional) is a type of string
  description = null
  # ip_addresses - (required) is a type of set of string
  ip_addresses = []
  # is_inheritance_allowed - (optional) is a type of bool
  is_inheritance_allowed = null
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
variable "description" {
  description = "(optional) - IP set description"
  type        = string
  default     = null
}

variable "ip_addresses" {
  description = "(required) - A set of IP address, CIDR, IP range objects"
  type        = set(string)
}

variable "is_inheritance_allowed" {
  description = "(optional) - Allows visibility in underlying scopes (Default is true)"
  type        = bool
  default     = null
}

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

### Resource

```terraform
resource "vcd_nsxv_ip_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # ip_addresses - (required) is a type of set of string
  ip_addresses = var.ip_addresses
  # is_inheritance_allowed - (optional) is a type of bool
  is_inheritance_allowed = var.is_inheritance_allowed
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
output "id" {
  description = "returns a string"
  value       = vcd_nsxv_ip_set.this.id
}

output "this" {
  value = vcd_nsxv_ip_set.this
}
```

[top](#index)