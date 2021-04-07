# thunder_fw_helper_sessions

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
module "thunder_fw_helper_sessions" {
  source = "./modules/thunder/r/thunder_fw_helper_sessions"

  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # limit - (optional) is a type of number
  limit = null
  # mode - (optional) is a type of string
  mode = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mode" {
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
resource "thunder_fw_helper_sessions" "this" {
  # idle_timeout - (optional) is a type of number
  idle_timeout = var.idle_timeout
  # limit - (optional) is a type of number
  limit = var.limit
  # mode - (optional) is a type of string
  mode = var.mode
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_helper_sessions.this.id
}

output "this" {
  value = thunder_fw_helper_sessions.this
}
```

[top](#index)