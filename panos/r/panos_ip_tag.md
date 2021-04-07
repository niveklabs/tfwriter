# panos_ip_tag

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
module "panos_ip_tag" {
  source = "./modules/panos/r/panos_ip_tag"

  # ip - (required) is a type of string
  ip = null
  # tags - (required) is a type of set of string
  tags = []
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required) - IP address to tag"
  type        = string
}

variable "tags" {
  description = "(required) - Tags"
  type        = set(string)
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_ip_tag" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # tags - (required) is a type of set of string
  tags = var.tags
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ip_tag.this.id
}

output "this" {
  value = panos_ip_tag.this
}
```

[top](#index)