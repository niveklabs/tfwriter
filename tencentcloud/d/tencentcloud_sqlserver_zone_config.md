# tencentcloud_sqlserver_zone_config

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
module "tencentcloud_sqlserver_zone_config" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_zone_config"

  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_sqlserver_zone_config" "this" {
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_zone_config.this.id
}

output "zone_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_zone_config.this.zone_list
}

output "this" {
  value = tencentcloud_sqlserver_zone_config.this
}
```

[top](#index)