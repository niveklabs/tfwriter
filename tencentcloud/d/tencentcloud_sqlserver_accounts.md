# tencentcloud_sqlserver_accounts

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
module "tencentcloud_sqlserver_accounts" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_accounts"

  # instance_id - (required) is a type of string
  instance_id = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - SQL server instance ID that the account belongs to."
  type        = string
}

variable "name" {
  description = "(optional) - Name of the SQL server account to be queried."
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
data "tencentcloud_sqlserver_accounts" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
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
  value       = data.tencentcloud_sqlserver_accounts.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_accounts.this.list
}

output "this" {
  value = tencentcloud_sqlserver_accounts.this
}
```

[top](#index)