# tencentcloud_tcr_tokens

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
module "tencentcloud_tcr_tokens" {
  source = "./modules/tencentcloud/d/tencentcloud_tcr_tokens"

  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # token_id - (optional) is a type of string
  token_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - ID of the instance that the token belongs to."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "token_id" {
  description = "(optional) - ID of the TCR token to query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcr_tokens" "this" {
  instance_id        = var.instance_id
  result_output_file = var.result_output_file
  token_id           = var.token_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcr_tokens.this.id
}

output "token_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcr_tokens.this.token_list
}

output "this" {
  value = tencentcloud_tcr_tokens.this
}
```

[top](#index)