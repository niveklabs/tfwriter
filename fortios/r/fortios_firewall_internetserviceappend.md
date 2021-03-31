# fortios_firewall_internetserviceappend

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
module "fortios_firewall_internetserviceappend" {
  source = "./modules/fortios/r/fortios_firewall_internetserviceappend"

  # append_port - (optional) is a type of number
  append_port = null
  # match_port - (optional) is a type of number
  match_port = null
}
```

[top](#index)

### Variables

```terraform
variable "append_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "match_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetserviceappend" "this" {
  append_port = var.append_port
  match_port  = var.match_port
}
```

[top](#index)

### Outputs

```terraform
output "append_port" {
  description = "returns a number"
  value       = fortios_firewall_internetserviceappend.this.append_port
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceappend.this.id
}

output "match_port" {
  description = "returns a number"
  value       = fortios_firewall_internetserviceappend.this.match_port
}

output "this" {
  value = fortios_firewall_internetserviceappend.this
}
```

[top](#index)