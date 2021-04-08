# vultr_ssh_key

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vultr_ssh_key" {
  source = "./modules/vultr/r/vultr_ssh_key"

  # name - (required) is a type of string
  name = null
  # ssh_key - (required) is a type of string
  ssh_key = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "ssh_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_ssh_key" "this" {
  # name - (required) is a type of string
  name = var.name
  # ssh_key - (required) is a type of string
  ssh_key = var.ssh_key
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_ssh_key.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_ssh_key.this.id
}

output "this" {
  value = vultr_ssh_key.this
}
```

[top](#index)