# cloudflare_custom_pages

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
module "cloudflare_custom_pages" {
  source = "./modules/cloudflare/r/cloudflare_custom_pages"

  # account_id - (optional) is a type of string
  account_id = null
  # state - (optional) is a type of string
  state = null
  # type - (required) is a type of string
  type = null
  # url - (required) is a type of string
  url = null
  # zone_id - (optional) is a type of string
  zone_id = null
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_custom_pages" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # state - (optional) is a type of string
  state = var.state
  # type - (required) is a type of string
  type = var.type
  # url - (required) is a type of string
  url = var.url
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_custom_pages.this.id
}

output "this" {
  value = cloudflare_custom_pages.this
}
```

[top](#index)