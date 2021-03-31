# cloudscale_server_group

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_server_group" {
  source = "./modules/cloudscale/r/cloudscale_server_group"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
  # zone_slug - (optional) is a type of string
  zone_slug = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_slug" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_server_group" "this" {
  name      = var.name
  type      = var.type
  zone_slug = var.zone_slug
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_server_group.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_server_group.this.id
}

output "zone_slug" {
  description = "returns a string"
  value       = cloudscale_server_group.this.zone_slug
}

output "this" {
  value = cloudscale_server_group.this
}
```

[top](#index)