# tencentcloud_ckafka_users

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
module "tencentcloud_ckafka_users" {
  source = "./modules/tencentcloud/d/tencentcloud_ckafka_users"

  # account_name - (optional) is a type of string
  account_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(optional) - Account name used when query ckafka users' infos. Could be a substr of user name."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - Id of the ckafka instance."
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
data "tencentcloud_ckafka_users" "this" {
  account_name       = var.account_name
  instance_id        = var.instance_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ckafka_users.this.id
}

output "user_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ckafka_users.this.user_list
}

output "this" {
  value = tencentcloud_ckafka_users.this
}
```

[top](#index)