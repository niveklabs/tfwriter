# fortios_firewall_iptranslation

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_iptranslation" {
  source = "./modules/fortios/r/fortios_firewall_iptranslation"

  # endip - (required) is a type of string
  endip = null
  # map_startip - (required) is a type of string
  map_startip = null
  # startip - (required) is a type of string
  startip = null
  # transid - (optional) is a type of number
  transid = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "endip" {
  description = "(required)"
  type        = string
}

variable "map_startip" {
  description = "(required)"
  type        = string
}

variable "startip" {
  description = "(required)"
  type        = string
}

variable "transid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_iptranslation" "this" {
  endip       = var.endip
  map_startip = var.map_startip
  startip     = var.startip
  transid     = var.transid
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_iptranslation.this.id
}

output "transid" {
  description = "returns a number"
  value       = fortios_firewall_iptranslation.this.transid
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_iptranslation.this.type
}

output "this" {
  value = fortios_firewall_iptranslation.this
}
```

[top](#index)