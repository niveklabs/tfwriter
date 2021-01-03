# bigip_sys_snmp

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_snmp" {
  source = "./modules/bigip/r/bigip_sys_snmp"

  # allowedaddresses - (optional) is a type of set of string
  allowedaddresses = []
  # sys_contact - (optional) is a type of string
  sys_contact = null
  # sys_location - (optional) is a type of string
  sys_location = null
}
```

[top](#index)

### Variables

```terraform
variable "allowedaddresses" {
  description = "(optional) - List of SNMP addresses"
  type        = set(string)
  default     = null
}

variable "sys_contact" {
  description = "(optional) - Contact Person email"
  type        = string
  default     = null
}

variable "sys_location" {
  description = "(optional) - Location of the F5 "
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_snmp" "this" {
  allowedaddresses = var.allowedaddresses
  sys_contact      = var.sys_contact
  sys_location     = var.sys_location
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_snmp.this.id
}

output "this" {
  value = bigip_sys_snmp.this
}
```

[top](#index)