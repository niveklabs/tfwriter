# tencentcloud_as_scaling_configs

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
module "tencentcloud_as_scaling_configs" {
  source = "./modules/tencentcloud/d/tencentcloud_as_scaling_configs"

  # configuration_id - (optional) is a type of string
  configuration_id = null
  # configuration_name - (optional) is a type of string
  configuration_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "configuration_id" {
  description = "(optional) - Launch configuration ID."
  type        = string
  default     = null
}

variable "configuration_name" {
  description = "(optional) - Launch configuration name."
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
data "tencentcloud_as_scaling_configs" "this" {
  # configuration_id - (optional) is a type of string
  configuration_id = var.configuration_id
  # configuration_name - (optional) is a type of string
  configuration_name = var.configuration_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "configuration_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_as_scaling_configs.this.configuration_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_as_scaling_configs.this.id
}

output "this" {
  value = tencentcloud_as_scaling_configs.this
}
```

[top](#index)