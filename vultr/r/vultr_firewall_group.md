# vultr_firewall_group

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_firewall_group" {
  source = "./modules/vultr/r/vultr_firewall_group"

  # description - (optional) is a type of string
  description = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_firewall_group" "this" {
  # description - (optional) is a type of string
  description = var.description
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_firewall_group.this.date_created
}

output "date_modified" {
  description = "returns a string"
  value       = vultr_firewall_group.this.date_modified
}

output "id" {
  description = "returns a string"
  value       = vultr_firewall_group.this.id
}

output "instance_count" {
  description = "returns a number"
  value       = vultr_firewall_group.this.instance_count
}

output "max_rule_count" {
  description = "returns a number"
  value       = vultr_firewall_group.this.max_rule_count
}

output "rule_count" {
  description = "returns a number"
  value       = vultr_firewall_group.this.rule_count
}

output "this" {
  value = vultr_firewall_group.this
}
```

[top](#index)