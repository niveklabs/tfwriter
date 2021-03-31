# avi_sslprofile

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
module "avi_sslprofile" {
  source = "./modules/avi/r/avi_sslprofile"

  # accepted_ciphers - (optional) is a type of string
  accepted_ciphers = null
  # cipher_enums - (optional) is a type of list of string
  cipher_enums = []
  # ciphersuites - (optional) is a type of string
  ciphersuites = null
  # description - (optional) is a type of string
  description = null
  # dhparam - (optional) is a type of string
  dhparam = null
  # enable_early_data - (optional) is a type of bool
  enable_early_data = null
  # enable_ssl_session_reuse - (optional) is a type of bool
  enable_ssl_session_reuse = null
  # name - (required) is a type of string
  name = null
  # prefer_client_cipher_ordering - (optional) is a type of bool
  prefer_client_cipher_ordering = null
  # send_close_notify - (optional) is a type of bool
  send_close_notify = null
  # ssl_session_timeout - (optional) is a type of number
  ssl_session_timeout = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  accepted_versions = [{
    type = null
  }]

  ssl_rating = [{
    compatibility_rating = null
    performance_rating   = null
    security_score       = null
  }]

  tags = [{
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accepted_ciphers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cipher_enums" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ciphersuites" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhparam" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_early_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ssl_session_reuse" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "prefer_client_cipher_ordering" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "send_close_notify" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssl_session_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accepted_versions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "ssl_rating" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      compatibility_rating = string
      performance_rating   = string
      security_score       = string
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_sslprofile" "this" {
  accepted_ciphers              = var.accepted_ciphers
  cipher_enums                  = var.cipher_enums
  ciphersuites                  = var.ciphersuites
  description                   = var.description
  dhparam                       = var.dhparam
  enable_early_data             = var.enable_early_data
  enable_ssl_session_reuse      = var.enable_ssl_session_reuse
  name                          = var.name
  prefer_client_cipher_ordering = var.prefer_client_cipher_ordering
  send_close_notify             = var.send_close_notify
  ssl_session_timeout           = var.ssl_session_timeout
  tenant_ref                    = var.tenant_ref
  type                          = var.type
  uuid                          = var.uuid

  dynamic "accepted_versions" {
    for_each = var.accepted_versions
    content {
      type = accepted_versions.value["type"]
    }
  }

  dynamic "ssl_rating" {
    for_each = var.ssl_rating
    content {
      compatibility_rating = ssl_rating.value["compatibility_rating"]
      performance_rating   = ssl_rating.value["performance_rating"]
      security_score       = ssl_rating.value["security_score"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      type  = tags.value["type"]
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_sslprofile.this.description
}

output "dhparam" {
  description = "returns a string"
  value       = avi_sslprofile.this.dhparam
}

output "id" {
  description = "returns a string"
  value       = avi_sslprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_sslprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_sslprofile.this.uuid
}

output "this" {
  value = avi_sslprofile.this
}
```

[top](#index)