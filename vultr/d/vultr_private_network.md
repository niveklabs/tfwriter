# vultr_private_network

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
module "vultr_private_network" {
  source = "./modules/vultr/d/vultr_private_network"


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
data "vultr_private_network" "this" {

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
  value       = data.vultr_private_network.this.date_created
}

output "description" {
  description = "returns a string"
  value       = data.vultr_private_network.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vultr_private_network.this.id
}

output "region" {
  description = "returns a string"
  value       = data.vultr_private_network.this.region
}

output "v4_subnet" {
  description = "returns a string"
  value       = data.vultr_private_network.this.v4_subnet
}

output "v4_subnet_mask" {
  description = "returns a number"
  value       = data.vultr_private_network.this.v4_subnet_mask
}

output "this" {
  value = vultr_private_network.this
}
```

[top](#index)