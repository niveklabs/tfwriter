# vultr_startup_script

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
module "vultr_startup_script" {
  source = "./modules/vultr/r/vultr_startup_script"

  # name - (required) is a type of string
  name = null
  # script - (required) is a type of string
  script = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "script" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_startup_script" "this" {
  # name - (required) is a type of string
  name = var.name
  # script - (required) is a type of string
  script = var.script
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_startup_script.this.date_created
}

output "date_modified" {
  description = "returns a string"
  value       = vultr_startup_script.this.date_modified
}

output "id" {
  description = "returns a string"
  value       = vultr_startup_script.this.id
}

output "this" {
  value = vultr_startup_script.this
}
```

[top](#index)