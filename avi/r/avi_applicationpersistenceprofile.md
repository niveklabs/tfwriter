# avi_applicationpersistenceprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_applicationpersistenceprofile" {
  source = "./modules/avi/r/avi_applicationpersistenceprofile"

  # description - (optional) is a type of string
  description = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # name - (required) is a type of string
  name = null
  # persistence_type - (required) is a type of string
  persistence_type = null
  # server_hm_down_recovery - (optional) is a type of string
  server_hm_down_recovery = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  app_cookie_persistence_profile = [{
    encryption_key = null
    prst_hdr_name  = null
    timeout        = null
  }]

  hdr_persistence_profile = [{
    prst_hdr_name = null
  }]

  http_cookie_persistence_profile = [{
    always_send_cookie = null
    cookie_name        = null
    encryption_key     = null
    key = [{
      aes_key  = null
      hmac_key = null
      name     = null
    }]
    timeout = null
  }]

  ip_persistence_profile = [{
    ip_mask               = null
    ip_persistent_timeout = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "persistence_type" {
  description = "(required)"
  type        = string
}

variable "server_hm_down_recovery" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_cookie_persistence_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      encryption_key = string
      prst_hdr_name  = string
      timeout        = number
    }
  ))
  default = []
}

variable "hdr_persistence_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      prst_hdr_name = string
    }
  ))
  default = []
}

variable "http_cookie_persistence_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      always_send_cookie = bool
      cookie_name        = string
      encryption_key     = string
      key = list(object(
        {
          aes_key  = string
          hmac_key = string
          name     = string
        }
      ))
      timeout = number
    }
  ))
  default = []
}

variable "ip_persistence_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip_mask               = number
      ip_persistent_timeout = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_applicationpersistenceprofile" "this" {
  description             = var.description
  is_federated            = var.is_federated
  name                    = var.name
  persistence_type        = var.persistence_type
  server_hm_down_recovery = var.server_hm_down_recovery
  tenant_ref              = var.tenant_ref
  uuid                    = var.uuid

  dynamic "app_cookie_persistence_profile" {
    for_each = var.app_cookie_persistence_profile
    content {
      encryption_key = app_cookie_persistence_profile.value["encryption_key"]
      prst_hdr_name  = app_cookie_persistence_profile.value["prst_hdr_name"]
      timeout        = app_cookie_persistence_profile.value["timeout"]
    }
  }

  dynamic "hdr_persistence_profile" {
    for_each = var.hdr_persistence_profile
    content {
      prst_hdr_name = hdr_persistence_profile.value["prst_hdr_name"]
    }
  }

  dynamic "http_cookie_persistence_profile" {
    for_each = var.http_cookie_persistence_profile
    content {
      always_send_cookie = http_cookie_persistence_profile.value["always_send_cookie"]
      cookie_name        = http_cookie_persistence_profile.value["cookie_name"]
      encryption_key     = http_cookie_persistence_profile.value["encryption_key"]
      timeout            = http_cookie_persistence_profile.value["timeout"]

      dynamic "key" {
        for_each = http_cookie_persistence_profile.value.key
        content {
          aes_key  = key.value["aes_key"]
          hmac_key = key.value["hmac_key"]
          name     = key.value["name"]
        }
      }

    }
  }

  dynamic "ip_persistence_profile" {
    for_each = var.ip_persistence_profile
    content {
      ip_mask               = ip_persistence_profile.value["ip_mask"]
      ip_persistent_timeout = ip_persistence_profile.value["ip_persistent_timeout"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_applicationpersistenceprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_applicationpersistenceprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_applicationpersistenceprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_applicationpersistenceprofile.this.uuid
}

output "this" {
  value = avi_applicationpersistenceprofile.this
}
```

[top](#index)