# wavefront_cloud_integration_tesla

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_cloud_integration_tesla" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_tesla"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # email - (required) is a type of string
  email = null
  # force_save - (optional) is a type of bool
  force_save = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # service - (optional) is a type of string
  service = null
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = null
}
```

[top](#index)

### Variables

```terraform
variable "additional_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "force_save" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_refresh_rate_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_tesla" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # email - (required) is a type of string
  email = var.email
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # service - (optional) is a type of string
  service = var.service
  # service_refresh_rate_in_minutes - (optional) is a type of number
  service_refresh_rate_in_minutes = var.service_refresh_rate_in_minutes
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_tesla.this.id
}

output "this" {
  value = wavefront_cloud_integration_tesla.this
}
```

[top](#index)