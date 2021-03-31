# alicloud_edas_application

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
module "alicloud_edas_application" {
  source = "./modules/alicloud/r/alicloud_edas_application"

  # application_name - (required) is a type of string
  application_name = null
  # build_pack_id - (optional) is a type of number
  build_pack_id = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # descriotion - (optional) is a type of string
  descriotion = null
  # ecu_info - (optional) is a type of list of string
  ecu_info = []
  # group_id - (optional) is a type of string
  group_id = null
  # health_check_url - (optional) is a type of string
  health_check_url = null
  # logical_region_id - (optional) is a type of string
  logical_region_id = null
  # package_type - (required) is a type of string
  package_type = null
  # package_version - (optional) is a type of string
  package_version = null
  # war_url - (optional) is a type of string
  war_url = null
}
```

[top](#index)

### Variables

```terraform
variable "application_name" {
  description = "(required)"
  type        = string
}

variable "build_pack_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "descriotion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ecu_info" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logical_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_type" {
  description = "(required)"
  type        = string
}

variable "package_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "war_url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_application" "this" {
  application_name  = var.application_name
  build_pack_id     = var.build_pack_id
  cluster_id        = var.cluster_id
  descriotion       = var.descriotion
  ecu_info          = var.ecu_info
  group_id          = var.group_id
  health_check_url  = var.health_check_url
  logical_region_id = var.logical_region_id
  package_type      = var.package_type
  package_version   = var.package_version
  war_url           = var.war_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_edas_application.this.id
}

output "this" {
  value = alicloud_edas_application.this
}
```

[top](#index)