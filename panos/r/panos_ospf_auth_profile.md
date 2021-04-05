# panos_ospf_auth_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_ospf_auth_profile" {
  source = "./modules/panos/r/panos_ospf_auth_profile"

  # auth_type - (optional) is a type of string
  auth_type = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # virtual_router - (required) is a type of string
  virtual_router = null

  md5_key = [{
    key       = null
    key_id    = null
    preferred = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_type" {
  description = "(optional) - The auth type"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "password" {
  description = "(optional) - The simple password"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required) - The virtual router"
  type        = string
}

variable "md5_key" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key       = string
      key_id    = number
      preferred = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_ospf_auth_profile" "this" {
  auth_type      = var.auth_type
  name           = var.name
  password       = var.password
  template       = var.template
  template_stack = var.template_stack
  virtual_router = var.virtual_router

  dynamic "md5_key" {
    for_each = var.md5_key
    content {
      key       = md5_key.value["key"]
      key_id    = md5_key.value["key_id"]
      preferred = md5_key.value["preferred"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ospf_auth_profile.this.id
}

output "md5_keys_enc" {
  description = "returns a list of object"
  value       = panos_ospf_auth_profile.this.md5_keys_enc
  sensitive   = true
}

output "password_enc" {
  description = "returns a string"
  value       = panos_ospf_auth_profile.this.password_enc
  sensitive   = true
}

output "this" {
  value = panos_ospf_auth_profile.this
}
```

[top](#index)