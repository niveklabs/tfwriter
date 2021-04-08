# vultr_region

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
module "vultr_region" {
  source = "./modules/vultr/d/vultr_region"


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
data "vultr_region" "this" {

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
output "city" {
  description = "returns a string"
  value       = data.vultr_region.this.city
}

output "continent" {
  description = "returns a string"
  value       = data.vultr_region.this.continent
}

output "country" {
  description = "returns a string"
  value       = data.vultr_region.this.country
}

output "id" {
  description = "returns a string"
  value       = data.vultr_region.this.id
}

output "options" {
  description = "returns a list of string"
  value       = data.vultr_region.this.options
}

output "this" {
  value = vultr_region.this
}
```

[top](#index)