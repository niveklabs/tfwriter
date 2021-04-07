# tencentcloud_monitor_policy_conditions

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
module "tencentcloud_monitor_policy_conditions" {
  source = "./modules/tencentcloud/d/tencentcloud_monitor_policy_conditions"

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
  description = "(optional) - Name of the policy name, support partial matching, eg:`Cloud Virtual Machine`,`Virtual`,`Cloud Load Banlancer-Private CLB Listener`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_monitor_policy_conditions" "this" {
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_monitor_policy_conditions.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_monitor_policy_conditions.this.list
}

output "this" {
  value = tencentcloud_monitor_policy_conditions.this
}
```

[top](#index)