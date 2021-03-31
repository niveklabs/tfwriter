# azurerm_media_streaming_endpoint

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
module "azurerm_media_streaming_endpoint" {
  source = "./modules/azurerm/r/azurerm_media_streaming_endpoint"

  # auto_start_enabled - (optional) is a type of bool
  auto_start_enabled = null
  # cdn_enabled - (optional) is a type of bool
  cdn_enabled = null
  # cdn_profile - (optional) is a type of string
  cdn_profile = null
  # cdn_provider - (optional) is a type of string
  cdn_provider = null
  # custom_host_names - (optional) is a type of set of string
  custom_host_names = []
  # description - (optional) is a type of string
  description = null
  # location - (required) is a type of string
  location = null
  # max_cache_age_seconds - (optional) is a type of number
  max_cache_age_seconds = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scale_units - (required) is a type of number
  scale_units = null
  # tags - (optional) is a type of map of string
  tags = {}

  access_control = [{
    akamai_signature_header_authentication_key = [{
      base64_key = null
      expiration = null
      identifier = null
    }]
    ip_allow = [{
      address              = null
      name                 = null
      subnet_prefix_length = null
    }]
  }]

  cross_site_access_policy = [{
    client_access_policy = null
    cross_domain_policy  = null
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
variable "auto_start_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cdn_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cdn_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cdn_provider" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_host_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_cache_age_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "media_services_account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "scale_units" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "access_control" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      akamai_signature_header_authentication_key = list(object(
        {
          base64_key = string
          expiration = string
          identifier = string
        }
      ))
      ip_allow = list(object(
        {
          address              = string
          name                 = string
          subnet_prefix_length = number
        }
      ))
    }
  ))
  default = []
}

variable "cross_site_access_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_access_policy = string
      cross_domain_policy  = string
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
resource "azurerm_media_streaming_endpoint" "this" {
  auto_start_enabled          = var.auto_start_enabled
  cdn_enabled                 = var.cdn_enabled
  cdn_profile                 = var.cdn_profile
  cdn_provider                = var.cdn_provider
  custom_host_names           = var.custom_host_names
  description                 = var.description
  location                    = var.location
  max_cache_age_seconds       = var.max_cache_age_seconds
  media_services_account_name = var.media_services_account_name
  name                        = var.name
  resource_group_name         = var.resource_group_name
  scale_units                 = var.scale_units
  tags                        = var.tags

  dynamic "access_control" {
    for_each = var.access_control
    content {

      dynamic "akamai_signature_header_authentication_key" {
        for_each = access_control.value.akamai_signature_header_authentication_key
        content {
          base64_key = akamai_signature_header_authentication_key.value["base64_key"]
          expiration = akamai_signature_header_authentication_key.value["expiration"]
          identifier = akamai_signature_header_authentication_key.value["identifier"]
        }
      }

      dynamic "ip_allow" {
        for_each = access_control.value.ip_allow
        content {
          address              = ip_allow.value["address"]
          name                 = ip_allow.value["name"]
          subnet_prefix_length = ip_allow.value["subnet_prefix_length"]
        }
      }

    }
  }

  dynamic "cross_site_access_policy" {
    for_each = var.cross_site_access_policy
    content {
      client_access_policy = cross_site_access_policy.value["client_access_policy"]
      cross_domain_policy  = cross_site_access_policy.value["cross_domain_policy"]
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
output "auto_start_enabled" {
  description = "returns a bool"
  value       = azurerm_media_streaming_endpoint.this.auto_start_enabled
}

output "cdn_profile" {
  description = "returns a string"
  value       = azurerm_media_streaming_endpoint.this.cdn_profile
}

output "cdn_provider" {
  description = "returns a string"
  value       = azurerm_media_streaming_endpoint.this.cdn_provider
}

output "host_name" {
  description = "returns a string"
  value       = azurerm_media_streaming_endpoint.this.host_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_media_streaming_endpoint.this.id
}

output "this" {
  value = azurerm_media_streaming_endpoint.this
}
```

[top](#index)