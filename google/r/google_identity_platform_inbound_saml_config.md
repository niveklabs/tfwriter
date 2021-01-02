# google_identity_platform_inbound_saml_config

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_identity_platform_inbound_saml_config" {
  source = "./modules/google/r/google_identity_platform_inbound_saml_config"

  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  idp_config = [{
    idp_certificates = [{
      x509_certificate = null
    }]
    idp_entity_id = null
    sign_request  = null
    sso_url       = null
  }]

  sp_config = [{
    callback_uri = null
    sp_certificates = [{
      x509_certificate = null
    }]
    sp_entity_id = null
  }]

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
variable "display_name" {
  description = "(required) - Human friendly display name."
  type        = string
}

variable "enabled" {
  description = "(optional) - If this config allows users to sign in with the provider."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the InboundSamlConfig resource. Must start with 'saml.' and can only have alphanumeric characters,\nhyphens, underscores or periods. The part after 'saml.' must also start with a lowercase letter, end with an\nalphanumeric character, and have at least 2 characters."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      idp_certificates = list(object(
        {
          x509_certificate = string
        }
      ))
      idp_entity_id = string
      sign_request  = bool
      sso_url       = string
    }
  ))
}

variable "sp_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      callback_uri = string
      sp_certificates = list(object(
        {
          x509_certificate = string
        }
      ))
      sp_entity_id = string
    }
  ))
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
resource "google_identity_platform_inbound_saml_config" "this" {
  display_name = var.display_name
  enabled      = var.enabled
  name         = var.name
  project      = var.project

  dynamic "idp_config" {
    for_each = var.idp_config
    content {
      idp_entity_id = idp_config.value["idp_entity_id"]
      sign_request  = idp_config.value["sign_request"]
      sso_url       = idp_config.value["sso_url"]

      dynamic "idp_certificates" {
        for_each = idp_config.value.idp_certificates
        content {
          x509_certificate = idp_certificates.value["x509_certificate"]
        }
      }

    }
  }

  dynamic "sp_config" {
    for_each = var.sp_config
    content {
      callback_uri = sp_config.value["callback_uri"]
      sp_entity_id = sp_config.value["sp_entity_id"]
    }
  }

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
output "id" {
  description = "returns a string"
  value       = google_identity_platform_inbound_saml_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_identity_platform_inbound_saml_config.this.project
}

output "this" {
  value = google_identity_platform_inbound_saml_config.this
}
```

[top](#index)