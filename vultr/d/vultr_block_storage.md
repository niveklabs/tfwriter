# vultr_block_storage

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
module "vultr_block_storage" {
  source = "./modules/vultr/d/vultr_block_storage"


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
data "vultr_block_storage" "this" {

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
output "attached_to_instance" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.attached_to_instance
}

output "cost" {
  description = "returns a number"
  value       = data.vultr_block_storage.this.cost
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.date_created
}

output "id" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.id
}

output "label" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.label
}

output "region" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.region
}

output "size_gb" {
  description = "returns a number"
  value       = data.vultr_block_storage.this.size_gb
}

output "status" {
  description = "returns a string"
  value       = data.vultr_block_storage.this.status
}

output "this" {
  value = vultr_block_storage.this
}
```

[top](#index)