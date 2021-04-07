# cloudflare_authenticated_origin_pulls_certificate

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
module "cloudflare_authenticated_origin_pulls_certificate" {
  source = "./modules/cloudflare/r/cloudflare_authenticated_origin_pulls_certificate"

  # certificate - (required) is a type of string
  certificate = null
  # private_key - (required) is a type of string
  private_key = null
  # type - (required) is a type of string
  type = null
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_authenticated_origin_pulls_certificate" "this" {
  # certificate - (required) is a type of string
  certificate = var.certificate
  # private_key - (required) is a type of string
  private_key = var.private_key
  # type - (required) is a type of string
  type = var.type
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "expires_on" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.expires_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.id
}

output "issuer" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.issuer
}

output "serial_number" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.serial_number
}

output "signature" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.signature
}

output "status" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.status
}

output "uploaded_on" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls_certificate.this.uploaded_on
}

output "this" {
  value = cloudflare_authenticated_origin_pulls_certificate.this
}
```

[top](#index)