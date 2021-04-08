# vultr_reverse_ipv6

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
module "vultr_reverse_ipv6" {
  source = "./modules/vultr/d/vultr_reverse_ipv6"


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
data "vultr_reverse_ipv6" "this" {

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
output "id" {
  description = "returns a string"
  value       = data.vultr_reverse_ipv6.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.vultr_reverse_ipv6.this.instance_id
}

output "ip" {
  description = "returns a string"
  value       = data.vultr_reverse_ipv6.this.ip
}

output "reverse" {
  description = "returns a string"
  value       = data.vultr_reverse_ipv6.this.reverse
}

output "this" {
  value = vultr_reverse_ipv6.this
}
```

[top](#index)