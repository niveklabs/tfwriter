# tencentcloud_cdh_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cdh_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_cdh_instance"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # host_name - (optional) is a type of string
  host_name = null
  # host_type - (optional) is a type of string
  host_type = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # prepaid_renew_flag - (optional) is a type of string
  prepaid_renew_flag = null
  # project_id - (optional) is a type of number
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The available zone for the CDH instance."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID`. The default is `PREPAID`."
  type        = string
  default     = null
}

variable "host_name" {
  description = "(optional) - The name of the CDH instance. The max length of host_name is 60."
  type        = string
  default     = null
}

variable "host_type" {
  description = "(optional) - The type of the CDH instance."
  type        = string
  default     = null
}

variable "prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance, NOTE: it only works when charge_type is set to `PREPAID`. Valid values are `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `11`, `12`, `24`, `36`."
  type        = number
  default     = null
}

variable "prepaid_renew_flag" {
  description = "(optional) - Auto renewal flag. Valid values: `NOTIFY_AND_AUTO_RENEW`: notify upon expiration and renew automatically, `NOTIFY_AND_MANUAL_RENEW`: notify upon expiration but do not renew automatically, `DISABLE_NOTIFY_AND_MANUAL_RENEW`: neither notify upon expiration nor renew automatically. Default value: `NOTIFY_AND_MANUAL_RENEW`. If this parameter is specified as `NOTIFY_AND_AUTO_RENEW`, the instance will be automatically renewed on a monthly basis if the account balance is sufficient. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project the instance belongs to, default to 0."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cdh_instance" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # host_name - (optional) is a type of string
  host_name = var.host_name
  # host_type - (optional) is a type of string
  host_type = var.host_type
  # prepaid_period - (optional) is a type of number
  prepaid_period = var.prepaid_period
  # prepaid_renew_flag - (optional) is a type of string
  prepaid_renew_flag = var.prepaid_renew_flag
  # project_id - (optional) is a type of number
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.create_time
}

output "cvm_instance_ids" {
  description = "returns a list of string"
  value       = tencentcloud_cdh_instance.this.cvm_instance_ids
}

output "expired_time" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.expired_time
}

output "host_name" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.host_name
}

output "host_resource" {
  description = "returns a list of object"
  value       = tencentcloud_cdh_instance.this.host_resource
}

output "host_state" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.host_state
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.id
}

output "prepaid_renew_flag" {
  description = "returns a string"
  value       = tencentcloud_cdh_instance.this.prepaid_renew_flag
}

output "this" {
  value = tencentcloud_cdh_instance.this
}
```

[top](#index)