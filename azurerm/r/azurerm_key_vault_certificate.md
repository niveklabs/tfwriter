# azurerm_key_vault_certificate

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_key_vault_certificate" {
  source = "./modules/azurerm/r/azurerm_key_vault_certificate"

  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  certificate = [{
    contents = null
    password = null
  }]

  certificate_policy = [{
    issuer_parameters = [{
      name = null
    }]
    key_properties = [{
      exportable = null
      key_size   = null
      key_type   = null
      reuse_key  = null
    }]
    lifetime_action = [{
      action = [{
        action_type = null
      }]
      trigger = [{
        days_before_expiry  = null
        lifetime_percentage = null
      }]
    }]
    secret_properties = [{
      content_type = null
    }]
    x509_certificate_properties = [{
      extended_key_usage = []
      key_usage          = []
      subject            = null
      subject_alternative_names = [{
        dns_names = []
        emails    = []
        upns      = []
      }]
      validity_in_months = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      contents = string
      password = string
    }
  ))
  default = []
}

variable "certificate_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      issuer_parameters = list(object(
        {
          name = string
        }
      ))
      key_properties = list(object(
        {
          exportable = bool
          key_size   = number
          key_type   = string
          reuse_key  = bool
        }
      ))
      lifetime_action = list(object(
        {
          action = list(object(
            {
              action_type = string
            }
          ))
          trigger = list(object(
            {
              days_before_expiry  = number
              lifetime_percentage = number
            }
          ))
        }
      ))
      secret_properties = list(object(
        {
          content_type = string
        }
      ))
      x509_certificate_properties = list(object(
        {
          extended_key_usage = list(string)
          key_usage          = list(string)
          subject            = string
          subject_alternative_names = list(object(
            {
              dns_names = set(string)
              emails    = set(string)
              upns      = set(string)
            }
          ))
          validity_in_months = number
        }
      ))
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_key_vault_certificate" "this" {
  key_vault_id = var.key_vault_id
  name         = var.name
  tags         = var.tags

  dynamic "certificate" {
    for_each = var.certificate
    content {
      contents = certificate.value["contents"]
      password = certificate.value["password"]
    }
  }

  dynamic "certificate_policy" {
    for_each = var.certificate_policy
    content {

      dynamic "issuer_parameters" {
        for_each = certificate_policy.value.issuer_parameters
        content {
          name = issuer_parameters.value["name"]
        }
      }

      dynamic "key_properties" {
        for_each = certificate_policy.value.key_properties
        content {
          exportable = key_properties.value["exportable"]
          key_size   = key_properties.value["key_size"]
          key_type   = key_properties.value["key_type"]
          reuse_key  = key_properties.value["reuse_key"]
        }
      }

      dynamic "lifetime_action" {
        for_each = certificate_policy.value.lifetime_action
        content {

          dynamic "action" {
            for_each = lifetime_action.value.action
            content {
              action_type = action.value["action_type"]
            }
          }

          dynamic "trigger" {
            for_each = lifetime_action.value.trigger
            content {
              days_before_expiry  = trigger.value["days_before_expiry"]
              lifetime_percentage = trigger.value["lifetime_percentage"]
            }
          }

        }
      }

      dynamic "secret_properties" {
        for_each = certificate_policy.value.secret_properties
        content {
          content_type = secret_properties.value["content_type"]
        }
      }

      dynamic "x509_certificate_properties" {
        for_each = certificate_policy.value.x509_certificate_properties
        content {
          extended_key_usage = x509_certificate_properties.value["extended_key_usage"]
          key_usage          = x509_certificate_properties.value["key_usage"]
          subject            = x509_certificate_properties.value["subject"]
          validity_in_months = x509_certificate_properties.value["validity_in_months"]

          dynamic "subject_alternative_names" {
            for_each = x509_certificate_properties.value.subject_alternative_names
            content {
              dns_names = subject_alternative_names.value["dns_names"]
              emails    = subject_alternative_names.value["emails"]
              upns      = subject_alternative_names.value["upns"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_attribute" {
  description = "returns a list of object"
  value       = azurerm_key_vault_certificate.this.certificate_attribute
}

output "certificate_data" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.certificate_data
}

output "certificate_data_base64" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.certificate_data_base64
}

output "id" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.secret_id
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.thumbprint
}

output "version" {
  description = "returns a string"
  value       = azurerm_key_vault_certificate.this.version
}

output "this" {
  value = azurerm_key_vault_certificate.this
}
```

[top](#index)