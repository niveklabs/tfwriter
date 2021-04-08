# vultr_instance_ipv4

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
module "vultr_instance_ipv4" {
  source = "./modules/vultr/d/vultr_instance_ipv4"


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
data "vultr_instance_ipv4" "this" {

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
output "gateway" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.instance_id
}

output "ip" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.ip
}

output "netmask" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.netmask
}

output "reverse" {
  description = "returns a string"
  value       = data.vultr_instance_ipv4.this.reverse
}

output "this" {
  value = vultr_instance_ipv4.this
}
```

[top](#index)