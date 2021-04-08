# vultr_startup_script

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
module "vultr_startup_script" {
  source = "./modules/vultr/d/vultr_startup_script"


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
data "vultr_startup_script" "this" {

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
  value       = data.vultr_startup_script.this.date_created
}

output "date_modified" {
  description = "returns a string"
  value       = data.vultr_startup_script.this.date_modified
}

output "id" {
  description = "returns a string"
  value       = data.vultr_startup_script.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vultr_startup_script.this.name
}

output "script" {
  description = "returns a string"
  value       = data.vultr_startup_script.this.script
}

output "type" {
  description = "returns a string"
  value       = data.vultr_startup_script.this.type
}

output "this" {
  value = vultr_startup_script.this
}
```

[top](#index)