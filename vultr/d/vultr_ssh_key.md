# vultr_ssh_key

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
module "vultr_ssh_key" {
  source = "./modules/vultr/d/vultr_ssh_key"


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
data "vultr_ssh_key" "this" {

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
  value       = data.vultr_ssh_key.this.date_created
}

output "id" {
  description = "returns a string"
  value       = data.vultr_ssh_key.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vultr_ssh_key.this.name
}

output "ssh_key" {
  description = "returns a string"
  value       = data.vultr_ssh_key.this.ssh_key
}

output "this" {
  value = vultr_ssh_key.this
}
```

[top](#index)