# vultr_snapshot

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
module "vultr_snapshot" {
  source = "./modules/vultr/d/vultr_snapshot"


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
data "vultr_snapshot" "this" {

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
output "app_id" {
  description = "returns a number"
  value       = data.vultr_snapshot.this.app_id
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_snapshot.this.date_created
}

output "description" {
  description = "returns a string"
  value       = data.vultr_snapshot.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vultr_snapshot.this.id
}

output "os_id" {
  description = "returns a number"
  value       = data.vultr_snapshot.this.os_id
}

output "size" {
  description = "returns a number"
  value       = data.vultr_snapshot.this.size
}

output "status" {
  description = "returns a string"
  value       = data.vultr_snapshot.this.status
}

output "this" {
  value = vultr_snapshot.this
}
```

[top](#index)