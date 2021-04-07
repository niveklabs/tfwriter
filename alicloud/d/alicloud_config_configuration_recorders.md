# alicloud_config_configuration_recorders

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_config_configuration_recorders" {
  source = "./modules/alicloud/d/alicloud_config_configuration_recorders"

  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_config_configuration_recorders" "this" {
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_config_configuration_recorders.this.id
}

output "recorders" {
  description = "returns a list of object"
  value       = data.alicloud_config_configuration_recorders.this.recorders
}

output "this" {
  value = alicloud_config_configuration_recorders.this
}
```

[top](#index)