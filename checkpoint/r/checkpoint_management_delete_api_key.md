# checkpoint_management_delete_api_key

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
module "checkpoint_management_delete_api_key" {
  source = "./modules/checkpoint/r/checkpoint_management_delete_api_key"

  # admin_name - (optional) is a type of string
  admin_name = null
  # admin_uid - (optional) is a type of string
  admin_uid = null
  # api_key - (optional) is a type of string
  api_key = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_name" {
  description = "(optional) - Administrator name to generate API key for."
  type        = string
  default     = null
}

variable "admin_uid" {
  description = "(optional) - Administrator uid to generate API key for."
  type        = string
  default     = null
}

variable "api_key" {
  description = "(optional) - API key to be deleted."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_delete_api_key" "this" {
  # admin_name - (optional) is a type of string
  admin_name = var.admin_name
  # admin_uid - (optional) is a type of string
  admin_uid = var.admin_uid
  # api_key - (optional) is a type of string
  api_key = var.api_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_delete_api_key.this.id
}

output "this" {
  value = checkpoint_management_delete_api_key.this
}
```

[top](#index)