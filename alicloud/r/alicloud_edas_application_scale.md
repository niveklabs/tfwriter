# alicloud_edas_application_scale

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
module "alicloud_edas_application_scale" {
  source = "./modules/alicloud/r/alicloud_edas_application_scale"

  # app_id - (required) is a type of string
  app_id = null
  # deploy_group - (required) is a type of string
  deploy_group = null
  # ecu_info - (required) is a type of list of string
  ecu_info = []
  # force_status - (optional) is a type of bool
  force_status = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "deploy_group" {
  description = "(required)"
  type        = string
}

variable "ecu_info" {
  description = "(required)"
  type        = list(string)
}

variable "force_status" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_application_scale" "this" {
  app_id       = var.app_id
  deploy_group = var.deploy_group
  ecu_info     = var.ecu_info
  force_status = var.force_status
}
```

[top](#index)

### Outputs

```terraform
output "ecc_info" {
  description = "returns a string"
  value       = alicloud_edas_application_scale.this.ecc_info
}

output "id" {
  description = "returns a string"
  value       = alicloud_edas_application_scale.this.id
}

output "this" {
  value = alicloud_edas_application_scale.this
}
```

[top](#index)