# fortios_firewall_internetservicedefinition

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_internetservicedefinition" {
  source = "./modules/fortios/r/fortios_firewall_internetservicedefinition"

  # fosid - (optional) is a type of number
  fosid = null

  entry = [{
    category_id = null
    name        = null
    port        = null
    protocol    = null
    seq_num     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "entry" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category_id = number
      name        = string
      port        = number
      protocol    = number
      seq_num     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetservicedefinition" "this" {
  fosid = var.fosid

  dynamic "entry" {
    for_each = var.entry
    content {
      category_id = entry.value["category_id"]
      name        = entry.value["name"]
      port        = entry.value["port"]
      protocol    = entry.value["protocol"]
      seq_num     = entry.value["seq_num"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetservicedefinition.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicedefinition.this.id
}

output "this" {
  value = fortios_firewall_internetservicedefinition.this
}
```

[top](#index)