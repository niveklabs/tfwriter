# tencentcloud_reserved_instance_configs

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
module "tencentcloud_reserved_instance_configs" {
  source = "./modules/tencentcloud/d/tencentcloud_reserved_instance_configs"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # duration - (optional) is a type of number
  duration = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the reserved instance locates at."
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional) - Validity period of the reserved instance. Valid values are `31536000`(1 year) and `94608000`(3 years)."
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(optional) - The type of reserved instance."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_reserved_instance_configs" "this" {
  availability_zone  = var.availability_zone
  duration           = var.duration
  instance_type      = var.instance_type
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "config_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_reserved_instance_configs.this.config_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_reserved_instance_configs.this.id
}

output "this" {
  value = tencentcloud_reserved_instance_configs.this
}
```

[top](#index)