# thunder_fw_clear_session_filter

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
module "thunder_fw_clear_session_filter" {
  source = "./modules/thunder/r/thunder_fw_clear_session_filter"

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
resource "thunder_fw_clear_session_filter" "this" {
  status = var.status
  uuid   = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_clear_session_filter.this.id
}

output "this" {
  value = thunder_fw_clear_session_filter.this
}
```

[top](#index)