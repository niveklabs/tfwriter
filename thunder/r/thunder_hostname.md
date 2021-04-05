# thunder_hostname

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_hostname" {
  source = "./modules/thunder/r/thunder_hostname"

  # uuid - (optional) is a type of string
  uuid = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_hostname" "this" {
  uuid  = var.uuid
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_hostname.this.id
}

output "this" {
  value = thunder_hostname.this
}
```

[top](#index)