# vultr_reserved_ip

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
module "vultr_reserved_ip" {
  source = "./modules/vultr/d/vultr_reserved_ip"


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
data "vultr_reserved_ip" "this" {

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
  value       = data.vultr_reserved_ip.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.vultr_reserved_ip.this.instance_id
}

output "ip_type" {
  description = "returns a string"
  value       = data.vultr_reserved_ip.this.ip_type
}

output "label" {
  description = "returns a string"
  value       = data.vultr_reserved_ip.this.label
}

output "region" {
  description = "returns a string"
  value       = data.vultr_reserved_ip.this.region
}

output "subnet" {
  description = "returns a string"
  value       = data.vultr_reserved_ip.this.subnet
}

output "subnet_size" {
  description = "returns a number"
  value       = data.vultr_reserved_ip.this.subnet_size
}

output "this" {
  value = vultr_reserved_ip.this
}
```

[top](#index)