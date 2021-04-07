# tencentcloud_redis_zone_config

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_redis_zone_config" {
  source = "./modules/tencentcloud/d/tencentcloud_redis_zone_config"

  # region - (optional) is a type of string
  region = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # type_id - (optional) is a type of number
  type_id = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(optional) - Name of a region. If this value is not set, the current region getting from provider's configuration will be used."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "type_id" {
  description = "(optional) - Instance type ID."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_redis_zone_config" "this" {
  region             = var.region
  result_output_file = var.result_output_file
  type_id            = var.type_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_redis_zone_config.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_redis_zone_config.this.list
}

output "this" {
  value = tencentcloud_redis_zone_config.this
}
```

[top](#index)