# wavefront_cloud_integration_ec2

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
module "wavefront_cloud_integration_ec2" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_ec2"

  # additional_tags - (optional) is a type of map of string
  additional_tags = {}
  # external_id - (required) is a type of string
  external_id = null
  # force_save - (optional) is a type of bool
  force_save = null
  # hostname_tags - (optional) is a type of set of string
  hostname_tags = []
  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
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

variable "external_id" {
  description = "(required)"
  type        = string
}

variable "force_save" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hostname_tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
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
resource "wavefront_cloud_integration_ec2" "this" {
  # additional_tags - (optional) is a type of map of string
  additional_tags = var.additional_tags
  # external_id - (required) is a type of string
  external_id = var.external_id
  # force_save - (optional) is a type of bool
  force_save = var.force_save
  # hostname_tags - (optional) is a type of set of string
  hostname_tags = var.hostname_tags
  # name - (required) is a type of string
  name = var.name
  # role_arn - (required) is a type of string
  role_arn = var.role_arn
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
  value       = wavefront_cloud_integration_ec2.this.id
}

output "this" {
  value = wavefront_cloud_integration_ec2.this
}
```

[top](#index)