# thunder_fw_tcp_reset_on_error

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
module "thunder_fw_tcp_reset_on_error" {
  source = "./modules/thunder/r/thunder_fw_tcp_reset_on_error"

  # enable - (optional) is a type of number
  enable = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_tcp_reset_on_error" "this" {
  # enable - (optional) is a type of number
  enable = var.enable
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_tcp_reset_on_error.this.id
}

output "this" {
  value = thunder_fw_tcp_reset_on_error.this
}
```

[top](#index)