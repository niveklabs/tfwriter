# azurerm_key_vault_certificate_issuer

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_key_vault_certificate_issuer" {
  source = "./modules/azurerm/r/azurerm_key_vault_certificate_issuer"

  # account_id - (optional) is a type of string
  account_id = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null
  # org_id - (optional) is a type of string
  org_id = null
  # password - (optional) is a type of string
  password = null
  # provider_name - (required) is a type of string
  provider_name = null

  admin = [{
    email_address = null
    first_name    = null
    last_name     = null
    phone         = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "org_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_name" {
  description = "(required)"
  type        = string
}

variable "admin" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      email_address = string
      first_name    = string
      last_name     = string
      phone         = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_key_vault_certificate_issuer" "this" {
  account_id    = var.account_id
  key_vault_id  = var.key_vault_id
  name          = var.name
  org_id        = var.org_id
  password      = var.password
  provider_name = var.provider_name

  dynamic "admin" {
    for_each = var.admin
    content {
      email_address = admin.value["email_address"]
      first_name    = admin.value["first_name"]
      last_name     = admin.value["last_name"]
      phone         = admin.value["phone"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate_issuer.this.id
}

output "this" {
  value = azurerm_key_vault_certificate_issuer.this
}
```

[top](#index)