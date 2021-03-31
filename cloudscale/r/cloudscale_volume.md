# cloudscale_volume

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
module "cloudscale_volume" {
  source = "./modules/cloudscale/r/cloudscale_volume"

  # name - (required) is a type of string
  name = null
  # server_uuids - (optional) is a type of list of string
  server_uuids = []
  # size_gb - (required) is a type of number
  size_gb = null
  # type - (optional) is a type of string
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

variable "server_uuids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "size_gb" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "cloudscale_volume" "this" {
  name         = var.name
  server_uuids = var.server_uuids
  size_gb      = var.size_gb
  type         = var.type
  zone_slug    = var.zone_slug
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_volume.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_volume.this.id
}

output "zone_slug" {
  description = "returns a string"
  value       = cloudscale_volume.this.zone_slug
}

output "this" {
  value = cloudscale_volume.this
}
```

[top](#index)