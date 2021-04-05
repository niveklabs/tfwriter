# panos_ip_tag

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "panos_ip_tag" {
  source = "./modules/panos/d/panos_ip_tag"

  # ip - (optional) is a type of string
  ip = null
  # tag - (optional) is a type of string
  tag = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(optional) - Optionally filter on just this single IP address"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional) - Optionally filter on just this single tag"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_ip_tag" "this" {
  ip   = var.ip
  tag  = var.tag
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.panos_ip_tag.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.panos_ip_tag.this.id
}

output "total" {
  description = "returns a number"
  value       = data.panos_ip_tag.this.total
}

output "this" {
  value = panos_ip_tag.this
}
```

[top](#index)