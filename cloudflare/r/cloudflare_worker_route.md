# cloudflare_worker_route

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
module "cloudflare_worker_route" {
  source = "./modules/cloudflare/r/cloudflare_worker_route"

  # pattern - (required) is a type of string
  pattern = null
  # script_name - (optional) is a type of string
  script_name = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "pattern" {
  description = "(required)"
  type        = string
}

variable "script_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_worker_route" "this" {
  pattern     = var.pattern
  script_name = var.script_name
  zone_id     = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_worker_route.this.id
}

output "this" {
  value = cloudflare_worker_route.this
}
```

[top](#index)