# alicloud_cs_application

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_application" {
  source = "./modules/alicloud/r/alicloud_cs_application"

  # blue_green - (optional) is a type of bool
  blue_green = null
  # blue_green_confirm - (optional) is a type of bool
  blue_green_confirm = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # description - (optional) is a type of string
  description = null
  # environment - (optional) is a type of map of string
  environment = {}
  # latest_image - (optional) is a type of bool
  latest_image = null
  # name - (required) is a type of string
  name = null
  # template - (required) is a type of string
  template = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "blue_green" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "blue_green_confirm" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "environment" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "latest_image" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_application" "this" {
  blue_green         = var.blue_green
  blue_green_confirm = var.blue_green_confirm
  cluster_name       = var.cluster_name
  description        = var.description
  environment        = var.environment
  latest_image       = var.latest_image
  name               = var.name
  template           = var.template
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "default_domain" {
  description = "returns a string"
  value       = alicloud_cs_application.this.default_domain
}

output "id" {
  description = "returns a string"
  value       = alicloud_cs_application.this.id
}

output "services" {
  description = "returns a list of object"
  value       = alicloud_cs_application.this.services
}

output "this" {
  value = alicloud_cs_application.this
}
```

[top](#index)