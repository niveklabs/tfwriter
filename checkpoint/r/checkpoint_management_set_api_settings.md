# checkpoint_management_set_api_settings

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_set_api_settings" {
  source = "./modules/checkpoint/r/checkpoint_management_set_api_settings"

  # accepted_api_calls_from - (optional) is a type of string
  accepted_api_calls_from = null
  # automatic_start - (optional) is a type of bool
  automatic_start = null
}
```

[top](#index)

### Variables

```terraform
variable "accepted_api_calls_from" {
  description = "(optional) - Clients allowed to connect to the API Server."
  type        = string
  default     = null
}

variable "automatic_start" {
  description = "(optional) - MGMT API will start after server will start."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_api_settings" "this" {
  # accepted_api_calls_from - (optional) is a type of string
  accepted_api_calls_from = var.accepted_api_calls_from
  # automatic_start - (optional) is a type of bool
  automatic_start = var.automatic_start
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_api_settings.this.id
}

output "this" {
  value = checkpoint_management_set_api_settings.this
}
```

[top](#index)