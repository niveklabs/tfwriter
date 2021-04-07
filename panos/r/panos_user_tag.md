# panos_user_tag

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
module "panos_user_tag" {
  source = "./modules/panos/r/panos_user_tag"

  # tags - (required) is a type of set of string
  tags = []
  # user - (required) is a type of string
  user = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(required) - Tags"
  type        = set(string)
}

variable "user" {
  description = "(required) - IP address to tag"
  type        = string
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
resource "panos_user_tag" "this" {
  # tags - (required) is a type of set of string
  tags = var.tags
  # user - (required) is a type of string
  user = var.user
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_user_tag.this.id
}

output "this" {
  value = panos_user_tag.this
}
```

[top](#index)