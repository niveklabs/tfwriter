# tencentcloud_protocol_template_groups

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
module "tencentcloud_protocol_template_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_protocol_template_groups"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the protocol template group to query."
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
data "tencentcloud_protocol_template_groups" "this" {
  name               = var.name
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "group_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_protocol_template_groups.this.group_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_protocol_template_groups.this.id
}

output "this" {
  value = tencentcloud_protocol_template_groups.this
}
```

[top](#index)