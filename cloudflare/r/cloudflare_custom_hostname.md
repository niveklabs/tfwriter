# cloudflare_custom_hostname

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
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_custom_hostname" {
  source = "./modules/cloudflare/r/cloudflare_custom_hostname"

  # custom_origin_server - (optional) is a type of string
  custom_origin_server = null
  # hostname - (required) is a type of string
  hostname = null
  # zone_id - (required) is a type of string
  zone_id = null

  ssl = [{
    certificate_authority = null
    cname_name            = null
    cname_target          = null
    custom_certificate    = null
    custom_key            = null
    method                = null
    settings = [{
      ciphers         = []
      http2           = null
      min_tls_version = null
      tls13           = null
    }]
    status   = null
    type     = null
    wildcard = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_origin_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "ssl" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      certificate_authority = string
      cname_name            = string
      cname_target          = string
      custom_certificate    = string
      custom_key            = string
      method                = string
      settings = list(object(
        {
          ciphers         = list(string)
          http2           = string
          min_tls_version = string
          tls13           = string
        }
      ))
      status   = string
      type     = string
      wildcard = bool
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_custom_hostname" "this" {
  custom_origin_server = var.custom_origin_server
  hostname             = var.hostname
  zone_id              = var.zone_id

  dynamic "ssl" {
    for_each = var.ssl
    content {
      certificate_authority = ssl.value["certificate_authority"]
      cname_name            = ssl.value["cname_name"]
      cname_target          = ssl.value["cname_target"]
      custom_certificate    = ssl.value["custom_certificate"]
      custom_key            = ssl.value["custom_key"]
      method                = ssl.value["method"]
      status                = ssl.value["status"]
      type                  = ssl.value["type"]
      wildcard              = ssl.value["wildcard"]

      dynamic "settings" {
        for_each = ssl.value.settings
        content {
          ciphers         = settings.value["ciphers"]
          http2           = settings.value["http2"]
          min_tls_version = settings.value["min_tls_version"]
          tls13           = settings.value["tls13"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_custom_hostname.this.id
}

output "ownership_verification" {
  description = "returns a map of string"
  value       = cloudflare_custom_hostname.this.ownership_verification
}

output "ownership_verification_http" {
  description = "returns a map of string"
  value       = cloudflare_custom_hostname.this.ownership_verification_http
}

output "status" {
  description = "returns a string"
  value       = cloudflare_custom_hostname.this.status
}

output "this" {
  value = cloudflare_custom_hostname.this
}
```

[top](#index)