# vultr_firewall_group

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vultr/d/vultr_firewall_group"


  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vultr_firewall_group" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = data.vultr_firewall_group.this.date_created
}

output "date_modified" {
  description = "returns a string"
  value       = data.vultr_firewall_group.this.date_modified
}

output "description" {
  description = "returns a string"
  value       = data.vultr_firewall_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vultr_firewall_group.this.id
}

output "instance_count" {
  description = "returns a number"
  value       = data.vultr_firewall_group.this.instance_count
}

output "max_rule_count" {
  description = "returns a number"
  value       = data.vultr_firewall_group.this.max_rule_count
}

output "rule_count" {
  description = "returns a number"
  value       = data.vultr_firewall_group.this.rule_count
}

output "this" {
  value = vultr_firewall_group.this
}
```

[top](#index)