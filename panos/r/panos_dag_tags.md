# panos_dag_tags

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_dag_tags" {
  source = "./modules/panos/r/panos_dag_tags"

  # vsys - (optional) is a type of string
  vsys = null

  register = [{
    ip   = null
    tags = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "vsys" {
  description = "(optional) - The vsys to config DAG tags for"
  type        = string
  default     = null
}

variable "register" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      ip   = string
      tags = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_dag_tags" "this" {
  vsys = var.vsys

  dynamic "register" {
    for_each = var.register
    content {
      ip   = register.value["ip"]
      tags = register.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_dag_tags.this.id
}

output "this" {
  value = panos_dag_tags.this
}
```

[top](#index)