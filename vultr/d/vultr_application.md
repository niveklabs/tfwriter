# vultr_application

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
module "vultr_application" {
  source = "./modules/vultr/d/vultr_application"


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
data "vultr_application" "this" {

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
output "deploy_name" {
  description = "returns a string"
  value       = data.vultr_application.this.deploy_name
}

output "id" {
  description = "returns a string"
  value       = data.vultr_application.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vultr_application.this.name
}

output "short_name" {
  description = "returns a string"
  value       = data.vultr_application.this.short_name
}

output "this" {
  value = vultr_application.this
}
```

[top](#index)