# oci_identity_user_capabilities_management

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_identity_user_capabilities_management" {
  source = "./modules/oci/r/oci_identity_user_capabilities_management"

  # can_use_api_keys - (optional) is a type of bool
  can_use_api_keys = null
  # can_use_auth_tokens - (optional) is a type of bool
  can_use_auth_tokens = null
  # can_use_console_password - (optional) is a type of bool
  can_use_console_password = null
  # can_use_customer_secret_keys - (optional) is a type of bool
  can_use_customer_secret_keys = null
  # can_use_smtp_credentials - (optional) is a type of bool
  can_use_smtp_credentials = null
  # user_id - (required) is a type of string
  user_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "can_use_api_keys" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "can_use_auth_tokens" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "can_use_console_password" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "can_use_customer_secret_keys" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "can_use_smtp_credentials" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_identity_user_capabilities_management" "this" {
  can_use_api_keys             = var.can_use_api_keys
  can_use_auth_tokens          = var.can_use_auth_tokens
  can_use_console_password     = var.can_use_console_password
  can_use_customer_secret_keys = var.can_use_customer_secret_keys
  can_use_smtp_credentials     = var.can_use_smtp_credentials
  user_id                      = var.user_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "can_use_api_keys" {
  description = "returns a bool"
  value       = oci_identity_user_capabilities_management.this.can_use_api_keys
}

output "can_use_auth_tokens" {
  description = "returns a bool"
  value       = oci_identity_user_capabilities_management.this.can_use_auth_tokens
}

output "can_use_console_password" {
  description = "returns a bool"
  value       = oci_identity_user_capabilities_management.this.can_use_console_password
}

output "can_use_customer_secret_keys" {
  description = "returns a bool"
  value       = oci_identity_user_capabilities_management.this.can_use_customer_secret_keys
}

output "can_use_smtp_credentials" {
  description = "returns a bool"
  value       = oci_identity_user_capabilities_management.this.can_use_smtp_credentials
}

output "id" {
  description = "returns a string"
  value       = oci_identity_user_capabilities_management.this.id
}

output "this" {
  value = oci_identity_user_capabilities_management.this
}
```

[top](#index)