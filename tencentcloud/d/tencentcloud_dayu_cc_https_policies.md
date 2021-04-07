# tencentcloud_dayu_cc_https_policies

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
module "tencentcloud_dayu_cc_https_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_dayu_cc_https_policies"

  # name - (optional) is a type of string
  name = null
  # policy_id - (optional) is a type of string
  policy_id = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the CC https policy to be queried."
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(optional) - Id of the CC https policy to be queried."
  type        = string
  default     = null
}

variable "resource_id" {
  description = "(required) - Id of the resource that the CC https policy works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the CC https policy works for, valid value is `bgpip`."
  type        = string
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
data "tencentcloud_dayu_cc_https_policies" "this" {
  name               = var.name
  policy_id          = var.policy_id
  resource_id        = var.resource_id
  resource_type      = var.resource_type
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dayu_cc_https_policies.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dayu_cc_https_policies.this.list
}

output "this" {
  value = tencentcloud_dayu_cc_https_policies.this
}
```

[top](#index)