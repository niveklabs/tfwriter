# tencentcloud_elasticsearch_instance

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
module "tencentcloud_elasticsearch_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_elasticsearch_instance"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # basic_security_type - (optional) is a type of number
  basic_security_type = null
  # charge_period - (optional) is a type of number
  charge_period = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # deploy_mode - (optional) is a type of number
  deploy_mode = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # license_type - (optional) is a type of string
  license_type = null
  # password - (required) is a type of string
  password = null
  # renew_flag - (optional) is a type of string
  renew_flag = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (required) is a type of string
  version = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  multi_zone_infos = [{
    availability_zone = null
    subnet_id         = null
  }]

  node_info_list = [{
    disk_size = null
    disk_type = null
    encrypt   = null
    node_num  = null
    node_type = null
    type      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - Availability zone."
  type        = string
}

variable "basic_security_type" {
  description = "(optional) - Whether to enable X-Pack security authentication in Basic Edition 6.8 and above. Valid values are `1` and `2`. `1` is disabled, `2` is enabled, and default value is `1`."
  type        = number
  default     = null
}

variable "charge_period" {
  description = "(optional) - The tenancy of the prepaid instance, and uint is month. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = number
  default     = null
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID` and `POSTPAID_BY_HOUR`."
  type        = string
  default     = null
}

variable "deploy_mode" {
  description = "(optional) - Cluster deployment mode. Valid values are `0` and `1`. `0` is single-AZ deployment, and `1` is multi-AZ deployment. Default value is `0`."
  type        = number
  default     = null
}

variable "instance_name" {
  description = "(optional) - Name of the instance, which can contain 1 to 50 English letters, Chinese characters, digits, dashes(-), or underscores(_)."
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional) - License type. Valid values are `oss`, `basic` and `platinum`. The default value is `platinum`."
  type        = string
  default     = null
}

variable "password" {
  description = "(required) - Password to an instance."
  type        = string
}

variable "renew_flag" {
  description = "(optional) - When enabled, the instance will be renew automatically when it reach the end of the prepaid tenancy. Valid values are `RENEW_FLAG_AUTO` and `RENEW_FLAG_MANUAL`. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required) - The ID of a VPC subnetwork."
  type        = string
}

variable "tags" {
  description = "(optional) - A mapping of tags to assign to the instance. For tag limits, please refer to [Use Limits](https://intl.cloud.tencent.com/document/product/651/13354)."
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required) - Version of the instance. Valid values are `5.6.4`, `6.4.3`, `6.8.2` and `7.5.1`."
  type        = string
}

variable "vpc_id" {
  description = "(required) - The ID of a VPC network."
  type        = string
}

variable "multi_zone_infos" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      availability_zone = string
      subnet_id         = string
    }
  ))
  default = []
}

variable "node_info_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      disk_size = number
      disk_type = string
      encrypt   = bool
      node_num  = number
      node_type = string
      type      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_elasticsearch_instance" "this" {
  availability_zone   = var.availability_zone
  basic_security_type = var.basic_security_type
  charge_period       = var.charge_period
  charge_type         = var.charge_type
  deploy_mode         = var.deploy_mode
  instance_name       = var.instance_name
  license_type        = var.license_type
  password            = var.password
  renew_flag          = var.renew_flag
  subnet_id           = var.subnet_id
  tags                = var.tags
  version             = var.version
  vpc_id              = var.vpc_id

  dynamic "multi_zone_infos" {
    for_each = var.multi_zone_infos
    content {
      availability_zone = multi_zone_infos.value["availability_zone"]
      subnet_id         = multi_zone_infos.value["subnet_id"]
    }
  }

  dynamic "node_info_list" {
    for_each = var.node_info_list
    content {
      disk_size = node_info_list.value["disk_size"]
      disk_type = node_info_list.value["disk_type"]
      encrypt   = node_info_list.value["encrypt"]
      node_num  = node_info_list.value["node_num"]
      node_type = node_info_list.value["node_type"]
      type      = node_info_list.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_elasticsearch_instance.this.create_time
}

output "elasticsearch_domain" {
  description = "returns a string"
  value       = tencentcloud_elasticsearch_instance.this.elasticsearch_domain
}

output "elasticsearch_port" {
  description = "returns a number"
  value       = tencentcloud_elasticsearch_instance.this.elasticsearch_port
}

output "elasticsearch_vip" {
  description = "returns a string"
  value       = tencentcloud_elasticsearch_instance.this.elasticsearch_vip
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_elasticsearch_instance.this.id
}

output "kibana_url" {
  description = "returns a string"
  value       = tencentcloud_elasticsearch_instance.this.kibana_url
}

output "this" {
  value = tencentcloud_elasticsearch_instance.this
}
```

[top](#index)