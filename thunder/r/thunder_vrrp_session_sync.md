# thunder_vrrp_session_sync

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
module "thunder_vrrp_session_sync" {
  source = "./modules/thunder/r/thunder_vrrp_session_sync"

  # action - (optional) is a type of string
  action = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
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
resource "thunder_vrrp_session_sync" "this" {
  # action - (optional) is a type of string
  action = var.action
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_vrrp_session_sync.this.id
}

output "this" {
  value = thunder_vrrp_session_sync.this
}
```

[top](#index)