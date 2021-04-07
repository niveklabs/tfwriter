# fortios_system_proxyarp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "fortios_system_proxyarp" {
  source = "./modules/fortios/d/fortios_system_proxyarp"

  # fosid - (required) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_proxyarp" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "end_ip" {
  description = "returns a string"
  value       = data.fortios_system_proxyarp.this.end_ip
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_proxyarp.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_proxyarp.this.interface
}

output "ip" {
  description = "returns a string"
  value       = data.fortios_system_proxyarp.this.ip
}

output "this" {
  value = fortios_system_proxyarp.this
}
```

[top](#index)