# cloudflare_byo_ip_prefix

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
module "cloudflare_byo_ip_prefix" {
  source = "./modules/cloudflare/r/cloudflare_byo_ip_prefix"

  # advertisement - (optional) is a type of string
  advertisement = null
  # description - (optional) is a type of string
  description = null
  # prefix_id - (required) is a type of string
  prefix_id = null
}
```

[top](#index)

### Variables

```terraform
variable "advertisement" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_byo_ip_prefix" "this" {
  advertisement = var.advertisement
  description   = var.description
  prefix_id     = var.prefix_id
}
```

[top](#index)

### Outputs

```terraform
output "advertisement" {
  description = "returns a string"
  value       = cloudflare_byo_ip_prefix.this.advertisement
}

output "description" {
  description = "returns a string"
  value       = cloudflare_byo_ip_prefix.this.description
}

output "id" {
  description = "returns a string"
  value       = cloudflare_byo_ip_prefix.this.id
}

output "this" {
  value = cloudflare_byo_ip_prefix.this
}
```

[top](#index)