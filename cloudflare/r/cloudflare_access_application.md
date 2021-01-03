# cloudflare_access_application

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_access_application" {
  source = "./modules/cloudflare/r/cloudflare_access_application"

  # account_id - (optional) is a type of string
  account_id = null
  # allowed_idps - (optional) is a type of list of string
  allowed_idps = []
  # auto_redirect_to_identity - (optional) is a type of bool
  auto_redirect_to_identity = null
  # domain - (required) is a type of string
  domain = null
  # enable_binding_cookie - (optional) is a type of bool
  enable_binding_cookie = null
  # name - (required) is a type of string
  name = null
  # session_duration - (optional) is a type of string
  session_duration = null
  # zone_id - (optional) is a type of string
  zone_id = null

  cors_headers = [{
    allow_all_headers = null
    allow_all_methods = null
    allow_all_origins = null
    allow_credentials = null
    allowed_headers   = []
    allowed_methods   = []
    allowed_origins   = []
    max_age           = null
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

variable "allowed_idps" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "auto_redirect_to_identity" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "enable_binding_cookie" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "session_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cors_headers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_all_headers = bool
      allow_all_methods = bool
      allow_all_origins = bool
      allow_credentials = bool
      allowed_headers   = set(string)
      allowed_methods   = set(string)
      allowed_origins   = set(string)
      max_age           = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_access_application" "this" {
  account_id                = var.account_id
  allowed_idps              = var.allowed_idps
  auto_redirect_to_identity = var.auto_redirect_to_identity
  domain                    = var.domain
  enable_binding_cookie     = var.enable_binding_cookie
  name                      = var.name
  session_duration          = var.session_duration
  zone_id                   = var.zone_id

  dynamic "cors_headers" {
    for_each = var.cors_headers
    content {
      allow_all_headers = cors_headers.value["allow_all_headers"]
      allow_all_methods = cors_headers.value["allow_all_methods"]
      allow_all_origins = cors_headers.value["allow_all_origins"]
      allow_credentials = cors_headers.value["allow_credentials"]
      allowed_headers   = cors_headers.value["allowed_headers"]
      allowed_methods   = cors_headers.value["allowed_methods"]
      allowed_origins   = cors_headers.value["allowed_origins"]
      max_age           = cors_headers.value["max_age"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = cloudflare_access_application.this.account_id
}

output "aud" {
  description = "returns a string"
  value       = cloudflare_access_application.this.aud
}

output "id" {
  description = "returns a string"
  value       = cloudflare_access_application.this.id
}

output "zone_id" {
  description = "returns a string"
  value       = cloudflare_access_application.this.zone_id
}

output "this" {
  value = cloudflare_access_application.this
}
```

[top](#index)