# tencentcloud_ssm_secrets

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
module "tencentcloud_ssm_secrets" {
  source = "./modules/tencentcloud/d/tencentcloud_ssm_secrets"

  # order_type - (optional) is a type of number
  order_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # secret_name - (optional) is a type of string
  secret_name = null
  # state - (optional) is a type of number
  state = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "order_type" {
  description = "(optional) - The order to sort the create time of secret. `0` - desc, `1` - asc. Default value is `0`."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(optional) - Secret name used to filter result."
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - Filter by state of secret. `0` - all secrets are queried, `1` - only Enabled secrets are queried, `2` - only Disabled secrets are queried, `3` - only PendingDelete secrets are queried."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags to filter secret."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ssm_secrets" "this" {
  # order_type - (optional) is a type of number
  order_type = var.order_type
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # secret_name - (optional) is a type of string
  secret_name = var.secret_name
  # state - (optional) is a type of number
  state = var.state
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ssm_secrets.this.id
}

output "secret_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ssm_secrets.this.secret_list
}

output "this" {
  value = tencentcloud_ssm_secrets.this
}
```

[top](#index)