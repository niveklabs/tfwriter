# alicloud_edas_application_deployment

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
module "alicloud_edas_application_deployment" {
  source = "./modules/alicloud/r/alicloud_edas_application_deployment"

  # app_id - (required) is a type of string
  app_id = null
  # group_id - (required) is a type of string
  group_id = null
  # package_version - (optional) is a type of string
  package_version = null
  # war_url - (required) is a type of string
  war_url = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "package_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "war_url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_application_deployment" "this" {
  app_id          = var.app_id
  group_id        = var.group_id
  package_version = var.package_version
  war_url         = var.war_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_edas_application_deployment.this.id
}

output "last_package_version" {
  description = "returns a string"
  value       = alicloud_edas_application_deployment.this.last_package_version
}

output "this" {
  value = alicloud_edas_application_deployment.this
}
```

[top](#index)