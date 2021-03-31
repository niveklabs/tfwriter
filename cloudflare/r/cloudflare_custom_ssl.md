# cloudflare_custom_ssl

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
module "cloudflare_custom_ssl" {
  source = "./modules/cloudflare/r/cloudflare_custom_ssl"

  # custom_ssl_options - (optional) is a type of map of string
  custom_ssl_options = {}
  # zone_id - (required) is a type of string
  zone_id = null

  custom_ssl_priority = [{
    id       = null
    priority = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_ssl_options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "custom_ssl_priority" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id       = string
      priority = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_custom_ssl" "this" {
  custom_ssl_options = var.custom_ssl_options
  zone_id            = var.zone_id

  dynamic "custom_ssl_priority" {
    for_each = var.custom_ssl_priority
    content {
      id       = custom_ssl_priority.value["id"]
      priority = custom_ssl_priority.value["priority"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "expires_on" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.expires_on
}

output "hosts" {
  description = "returns a list of string"
  value       = cloudflare_custom_ssl.this.hosts
}

output "id" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.id
}

output "issuer" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.issuer
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.modified_on
}

output "priority" {
  description = "returns a number"
  value       = cloudflare_custom_ssl.this.priority
}

output "signature" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.signature
}

output "status" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.status
}

output "uploaded_on" {
  description = "returns a string"
  value       = cloudflare_custom_ssl.this.uploaded_on
}

output "this" {
  value = cloudflare_custom_ssl.this
}
```

[top](#index)