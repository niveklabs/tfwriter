# vultr_plan

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
module "vultr_plan" {
  source = "./modules/vultr/d/vultr_plan"


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
data "vultr_plan" "this" {

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
output "bandwidth" {
  description = "returns a number"
  value       = data.vultr_plan.this.bandwidth
}

output "disk" {
  description = "returns a number"
  value       = data.vultr_plan.this.disk
}

output "id" {
  description = "returns a string"
  value       = data.vultr_plan.this.id
}

output "locations" {
  description = "returns a list of string"
  value       = data.vultr_plan.this.locations
}

output "monthly_cost" {
  description = "returns a number"
  value       = data.vultr_plan.this.monthly_cost
}

output "ram" {
  description = "returns a number"
  value       = data.vultr_plan.this.ram
}

output "type" {
  description = "returns a string"
  value       = data.vultr_plan.this.type
}

output "vcpu_count" {
  description = "returns a number"
  value       = data.vultr_plan.this.vcpu_count
}

output "this" {
  value = vultr_plan.this
}
```

[top](#index)