# tencentcloud_dayu_ddos_policy_cases

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
module "tencentcloud_dayu_ddos_policy_cases" {
  source = "./modules/tencentcloud/d/tencentcloud_dayu_ddos_policy_cases"

  # resource_type - (required) is a type of string
  resource_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # scene_id - (required) is a type of string
  scene_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_type" {
  description = "(required) - Type of the resource that the DDoS policy case works for, valid values are `bgpip`, `bgp`, `bgp-multip` and `net`."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "scene_id" {
  description = "(required) - ID of the DDoS policy case to be query."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_dayu_ddos_policy_cases" "this" {
  resource_type      = var.resource_type
  result_output_file = var.result_output_file
  scene_id           = var.scene_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dayu_ddos_policy_cases.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dayu_ddos_policy_cases.this.list
}

output "this" {
  value = tencentcloud_dayu_ddos_policy_cases.this
}
```

[top](#index)