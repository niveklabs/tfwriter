# dome9_iplist

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_iplist" {
  source = "./modules/dome9/d/dome9_iplist"


  items = [{
    comment = null
    ip      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "items" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment = string
      ip      = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "dome9_iplist" "this" {

  dynamic "items" {
    for_each = var.items
    content {
      # comment - (optional) is a type of string
      comment = items.value["comment"]
      # ip - (optional) is a type of string
      ip = items.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.dome9_iplist.this.description
}

output "id" {
  description = "returns a string"
  value       = data.dome9_iplist.this.id
}

output "name" {
  description = "returns a string"
  value       = data.dome9_iplist.this.name
}

output "this" {
  value = dome9_iplist.this
}
```

[top](#index)