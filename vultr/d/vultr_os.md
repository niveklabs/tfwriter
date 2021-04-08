# vultr_os

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
module "vultr_os" {
  source = "./modules/vultr/d/vultr_os"


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
data "vultr_os" "this" {

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
output "arch" {
  description = "returns a string"
  value       = data.vultr_os.this.arch
}

output "family" {
  description = "returns a string"
  value       = data.vultr_os.this.family
}

output "id" {
  description = "returns a string"
  value       = data.vultr_os.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vultr_os.this.name
}

output "this" {
  value = vultr_os.this
}
```

[top](#index)