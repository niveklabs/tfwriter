# thunder_fw_tcp_rst_close_immediate

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
module "thunder_fw_tcp_rst_close_immediate" {
  source = "./modules/thunder/r/thunder_fw_tcp_rst_close_immediate"

  # status - (optional) is a type of string
  status = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "status" {
  description = "(optional)"
  type        = string
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
resource "thunder_fw_tcp_rst_close_immediate" "this" {
  # status - (optional) is a type of string
  status = var.status
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_tcp_rst_close_immediate.this.id
}

output "this" {
  value = thunder_fw_tcp_rst_close_immediate.this
}
```

[top](#index)