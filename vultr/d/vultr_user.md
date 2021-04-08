# vultr_user

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
module "vultr_user" {
  source = "./modules/vultr/d/vultr_user"


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
data "vultr_user" "this" {

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
output "acl" {
  description = "returns a list of string"
  value       = data.vultr_user.this.acl
}

output "api_enabled" {
  description = "returns a bool"
  value       = data.vultr_user.this.api_enabled
}

output "email" {
  description = "returns a string"
  value       = data.vultr_user.this.email
}

output "id" {
  description = "returns a string"
  value       = data.vultr_user.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vultr_user.this.name
}

output "this" {
  value = vultr_user.this
}
```

[top](#index)